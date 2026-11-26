### Keep Column with after Refresh All 
	- Click any cell inside the table.
	- Go to Data → Queries & Connections, then right-click your query → Properties. (Or go to Table Design → Properties.)
	- Uncheck Adjust column width.
	- Click OK.
	

### Age Calculator File
	- Add data into source file then Refresh to see the change.
	
	
<h2 style="color:red;">My Red Heading# Power Query দিয়ে বয়স (বছর, মাস, দিন) বের করার ধাপ</h2>

	ধরা যাক, আপনার টেবিলে Name এবং Date of Birth (জন্ম তারিখ) নামে দুটি কলাম আছে।

## ধাপ ১: ডেটা Power Query-তে লোড করুন

	1. টেবিলের যেকোনো ঘরে ক্লিক করুন।
	2. Data → From Table/Range এ ক্লিক করুন।
	3. Power Query Editor খুলবে।

## ধাপ ২: Date of Birth কলামের Data Type ঠিক করুন

	1. Date of Birth কলামের হেডারের বাম পাশের আইকনে ক্লিক করুন।
	2. Date সিলেক্ট করুন।

## ধাপ ৩: আজকের তারিখ যোগ করুন

	1. Add Column → Custom Column এ ক্লিক করুন।
	2. কলামের নাম দিন: `Today`
	3. ফর্মুলা লিখুন:


Date.From(DateTime.LocalNow())


4. OK চাপুন।

## ধাপ ৪: বছর বের করুন

	Add Column → Custom Column এ গিয়ে নাম দিন `Years` এবং ফর্মুলা লিখুন:


	Date.Year([Today]) - Date.Year([Date of Birth]) 
	- (if Date.AddYears([Date of Birth], Date.Year([Today]) - Date.Year([Date of Birth])) > [Today] then 1 else 0)


	এই ফর্মুলা জন্মদিন এখনো না এলে এক বছর কমিয়ে দেয়, ফলে বছর নির্ভুল হয়।

## ধাপ ৫: মাস বের করুন

	Custom Column এ নাম দিন `Months` এবং ফর্মুলা:


	let
		afterYears = Date.AddYears([Date of Birth], [Years]),
		m = (Date.Year([Today]) - Date.Year(afterYears))  12 + Date.Month([Today]) - Date.Month(afterYears),
		adj = if Date.AddMonths(afterYears, m) > [Today] then m - 1 else m
	in
		adj


## ধাপ ৬: দিন বের করুন

	Custom Column এ নাম দিন `Days` এবং ফর্মুলা:


	Duration.Days([Today] - Date.AddMonths(Date.AddYears([Date of Birth], [Years]), [Months]))


## ধাপ ৭: একসাথে "বয়স" কলাম বানান (ঐচ্ছিক)

	Custom Column এ নাম দিন `Age` এবং ফর্মুলা:


	Text.From([Years]) & " Years " & Text.From([Months]) & " Months " & Text.From([Days]) & " Days"


	ফলাফল দেখতে এমন হবে: 56 Years 3 Months 12 Days

## ধাপ ৮: মোট দিন ও ঘণ্টা (আপনার স্ক্রিনশটের মতো)

	মোট দিন:

	Duration.Days([Today] - [Date of Birth])


	মোট ঘণ্টা:

	Duration.Days([Today] - [Date of Birth])  24


## ধাপ ৯: অপ্রয়োজনীয় কলাম মুছুন

	1. Today কলামটিতে রাইট-ক্লিক করুন।
	2. Remove সিলেক্ট করুন। (ধাপ ৭ ও ৮ শেষ হওয়ার পরে এটি করুন, নইলে ফর্মুলা কাজ করবে না।)

## ধাপ ১০: Excel-এ লোড করুন

	1. Home → Close & Load এ ক্লিক করুন।
	2. ফলাফল নতুন শিটে টেবিল আকারে আসবে।

## গুরুত্বপূর্ণ টিপস

	- কলামের নাম মিলিয়ে নিন: ফর্মুলায় `[Date of Birth]` লেখা আছে। আপনার কলামের নাম আলাদা হলে ফর্মুলায় সেই নাম বসান।
	- ক্যাপিটাল লেটার: Power Query-তে `Date.Year` এবং `date.year` আলাদা। বড়-ছোট হাতের অক্ষর হুবহু মেলাতে হবে।
	- অটো আপডেট: Data → Refresh All চাপলেই প্রতিদিনের তারিখ অনুযায়ী বয়স আপডেট হবে।
	- কলাম প্রস্থ: ফলাফলের কলাম সরু দেখালে আগের উত্তরে বলা Adjust column width বন্ধ করার পদ্ধতি অনুসরণ করুন।