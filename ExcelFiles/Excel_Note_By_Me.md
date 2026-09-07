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
