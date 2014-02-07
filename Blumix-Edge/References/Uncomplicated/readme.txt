Customizing Uncomplicated v1.x
==================================

Author: Rafa Cobreros rafacobreros@gmail.com
License: GPL
Original theme in: http://gnome-look.org/content/show.php/Uncomplicated?content=157986

Customization tips:
1.- Style for nautilus
2.- Style for tabs

NOTE:
- Some changes require close and open session after them
- Note that according to the theme you use the name of the folder where
  files are changed. (Uncomplicated, Uncomplicated-Mint or Uncomplicated-Orange)

-----------------------------------
* 1.- Select version for nautilus *
-----------------------------------
If you use nautilus 3.6.x not need to change anything in this section, however if you use nautilus 3.4 need change a line in gtk.css file.

Edit (gedit) the file ../Uncomplicated/gtk-3.0/gtk.css

go to the last line of the file, there are two options for nautilus:
	If you use nautilus 3.6.x (by default)
	@import url("nautilus36.css"); 

    If you use nautilus 3.4.x 
	@import url("nautilus34.css"); 

edit (please carefully) the corresponding line "@import" according to the version of nautilus you want,
to make it ONE of the two.
(beware of leaving only one of two)

@import url("nautilus36.css"); 
@import url("nautilus34.css");

------------------------------
* 2.- Select style for TABS *
------------------------------
Edit (gedit) the file ../Uncomplicated/gtk-3.0/gtk.css

Go to the line where it says
@import url("tabs-xxx.css");

and modify it according to the option you want, you have three options:

	1.- classic tabs
	@import url("tabs.css");

	2.- tab selected themed
	@import url("tabs-themed.css");

    3.- tabs semi rounded
    @import url("tabs-rounded.css");

	(Be careful to leave only ONE of the three,
	edit the 'import' line according to the style you want) 

@import url("tabs.css");
@import url("tabs-themed.css");
@import url("tabs-rounded.css");

