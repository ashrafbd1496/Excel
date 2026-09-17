## To use filter 
	select the first cell of a sheet then click - ctrl + shift + L 
	or use from Data > Filter.

## To Remove filter 
	mouse right click then clear filter or deselect from Data Menu.

## For removing Blank rows
	 filter> check blank from at last. then delete using ctrl- 
## Best font for excel is -
	 Segoe UI or Verdana , Calibri , Consolas

### Create Dropdown
	For creating dropdown - create a list> 
	select the cell want to where create dropdown.
	go to Data Menu> Data Validation>Choose List from dropdown>
	Select the list cells  

### Create Seiral Numbers
	for creating serial number use this formula and Drag down to end cell
		=IF(E9="","",COUNTIF($E$9:E9,"<>")) or 
		=IF(E20="","",COUNTA($E$20:E20))
	here E9 or E20 is the cell number of next column of 
	serial number. Serial Number will skip if the row is empty

### #VALUE! Error Fixing 
	কোনো ফর্মুলায় হঠাৎ #VALUE! আসলে তা সুন্দরভাবে লুকিয়ে রাখতে বা বিকল্প মান দেখাতে IFERROR করে ঠিক করা যায়। 
	=IFERROR(ফর্মুলা, 0) (এর অর্থ: মূল ফর্মুলায় ভুল/VALUE এরর আসলে এক্সেল সেখানে #VALUE! না দেখিয়ে ০ দেখাবে।)

### Excel Vlookup
	Formula - =VLOOKUP(lookup_value, table_array, col_index_num, [range_lookup])

	১. lookup_value (যা খুঁজছেন): যে তথ্যের ওপর ভিত্তি করে ডাটা খুঁজতে চান (যেমন: Roll Number বা Product ID)।

	২. table_array (যে টেবিলে খুঁজবেন): পুরো ডাটা টেবিলের রেঞ্জ (যেখান থেকে ডাটা খুঁজে বের করতে হবে)।

	৩. col_index_num (কত নম্বর কলামের ডাটা চান): আপনার কাঙ্ক্ষিত তথ্যটি টেবিলের কত নম্বর কলামে আছে? (১, ২, ৩... ইত্যাদি)।

	৪. range_lookup (শর্ত): একদম নিখুঁত ম্যাচ চাইলে 0 বা FALSE দিন। (৯৯% ক্ষেত্রে 0 ব্যবহার করা হয়)।

### XLOOKUP 
	Formula - =XLOOKUP(lookup_value, lookup_array, return_array, [if_not_found], [match_mode], [search_mode]) 

	a. lookup_value (যা খুঁজছেন): যে আইডি, নাম বা তথ্যের ওপর ভিত্তি করে ডাটা খুঁজতে চাই।

	b. lookup_array (যে কলামে আছে): খোঁজার বিষয়টি যে কলামে আছে, সেই কলামটি।

	c. return_array (যে কলামের রেজাল্ট চান): যে কলামে আপনার কাঙ্ক্ষিত উত্তরটি আছে, সেই কলামটি।

	d. [if_not_found] (ঐচ্ছিক): ডাটা না পাওয়া গেলে কী দেখাবে (যেমন: "Data Missing")।

	e. [match_mode] & [search_mode] (ঐচ্ছিক): বিশেষ ধরনের ম্যাচ বা ওপর/নিচ থেকে সার্চ করার জন্য ব্যবহৃত হয়।


### ফরম্যাটিং (Formatting)

 	-রো ও কলামের আকার নির্ধারণ: রো-এর উচ্চতা বা কলামের প্রস্থ সমন্বয় করতে Home > Format > Row Height অথবা Column Width নির্বাচন করুন।

 	-ডিফল্ট বা অটো সাইজ: সেলগুলোর আকার স্বয়ংক্রিয়ভাবে কনটেন্টের সাথে মিলিয়ে নিতে AutoFit অথবা আগের অবস্থায় ফেরাতে Default অপশন ব্যবহার করুন।

 	-ফরম্যাট কপি করা: একটি সেলের ফরম্যাটিং বা রঙের বিন্যাস অন্য সেলে প্রয়োগ করতে Format Painter ব্যবহার করুন।

	-ডেটা ও ফরম্যাট মোছা: কোনো সেলের তথ্য বা ডিজাইন পুরোপুরি মুছে ফেলতে Clear > Clear Formats অথবা Clear Contents অপশন বেছে নিন।

### freeze pane
	-রো ফ্রীজ করার জন্য যেই রো টা ফ্রীজ করতে চাই তার নিচের রো পর্যন্ত সিলেক্ট করতে হবে 
বা মাউস দিয়ে সেল পয়েন্ট করতে হবে।  এর পর ফ্রীজে মেনু থেকে ফ্রীজ করতে হবে।  

	- কলাম  ফ্রীজ করতে ও সেইম পদ্ধতি অবলম্বন করতে হবে।   

### Zoom Selection
	- সিলেক্টেড সেল গুলো Zoom করে দেখতে View মেনু থেকে Zoom to Selection 
  ### Cell Fill
	- To fill cell with random numbers we can use - =RANDBETWEEN(1, 100000)

### মিক্সড ডেটা থেকে টেক্সট ও নম্বর আলাদা করার সহজ নিয়ম:

	-প্রথমে যে সেলগুলোতে টেক্সট এবং নম্বর একসাথে মেশানো আছে, সেগুলো সিলেক্ট করুন।
	- কিবোর্ড থেকে Ctrl + G চাপুন, এতে Go To উইন্ডোটি ওপেন হবে। নিচের দিকে থাকা Special... অপশনে ক্লিক করুন এবং সেখান থেকে Constants বেছে নিন।

 	- এবার শুধু Text বক্সে টিক চিহ্ন দিন এবং বাকি অপশনগুলোর টিক তুলে দিন (Uncheck করুন)। এরপর OK চাপুন।

  	- এখন কিবোর্ড থেকে Ctrl + C চেপে কপি করুন এবং নতুন যে সেলে টেক্সটগুলো রাখতে চান, সেখানে গিয়ে পেস্ট করুন। 
  
  	- শুধু টেক্সটগুলো আলাদা হয়ে বসে যাবে। একইভাবে শুধু নম্বরগুলো আলাদা করতে চাইলে, কনস্ট্যান্টস অপশনে গিয়ে বাকিগুলো আনচেক করে কেবল Numbers বক্সে টিক দিয়ে কপি-পেস্ট করুন।

