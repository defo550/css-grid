# css-grid

A simple grid that I have used across multiple projects for the last year or so.  It is built using (SASS)[http://sass-lang.com/] and uses fractional ( or percentage ) widths.  


## Class Structure
 -  'row':	A 'row' groups the columns (i.e. 'span-') together in a horizontal row.
 - 	'row-spacing' : Performs the same as the above mentioned 'row', but it will add top and bottom margin to the 'row'.
 - 	'row-padding' : Also performs the same as 'row', but will add padding around the entire 'row', with the exception of the left side.
 - 	'span-[n]-[d]' 
 	- The 'span-' is the base class and is repsonsible for splitting a 'row' into sections.
 	- The '[n]-[d]' represents the fractional width that provides the width for our 'span-' selectors; hence the "n" and "d" (numerator and denominator).