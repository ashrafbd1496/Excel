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