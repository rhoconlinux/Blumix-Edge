SRCDIR = srcimg
MSRCDIR = ../metacity-1
BTNBASE = $(SRCDIR)/btnbase.xpm

BUTTON_XPMS = close-active.xpm close-inactive.xpm \
	close-pressed.xpm close-prelight.xpm \
	stick-active.xpm stick-inactive.xpm \
	stick-pressed.xpm stick-prelight.xpm \
	maximize-active.xpm maximize-inactive.xpm \
	maximize-pressed.xpm maximize-prelight.xpm \
	hide-active.xpm hide-inactive.xpm \
	hide-pressed.xpm hide-prelight.xpm \
	shade-active.xpm shade-inactive.xpm \
	shade-pressed.xpm shade-prelight.xpm \
	menu-active.xpm menu-inactive.xpm \
	menu-pressed.xpm menu-prelight.xpm

FRAME_XPMS = top-left-active.xpm top-left-inactive.xpm \
	title-1-active.xpm title-1-inactive.xpm \
	title-2-active.xpm title-2-inactive.xpm \
	title-3-active.xpm title-3-inactive.xpm \
	title-4-active.xpm title-4-inactive.xpm \
	title-5-active.xpm title-5-inactive.xpm \
	top-right-active.xpm top-right-inactive.xpm \
	bottom-right-active.xpm bottom-right-inactive.xpm \
	bottom-active.xpm bottom-inactive.xpm \
	bottom-left-active.xpm bottom-left-inactive.xpm \
	left-active.xpm left-inactive.xpm \
	right-active.xpm right-inactive.xpm \


# Top-level targets

all: $(FRAME_XPMS) $(BUTTON_XPMS)

clean:
	rm -f $(FRAME_XPMS) $(BUTTON_XPMS)


# Frame images are just copies

%-active.xpm: $(SRCDIR)/%.xpm
	cp -a $< $@

title-%-active.xpm: $(SRCDIR)/title-n.xpm
	cp -a $< $@

%-inactive.xpm: %-active.xpm
	cp -a $< $@


# Button images for Xfwm are based on the Metacity button images, but must be
# composited onto a base image to look right and hit the top left or top right
# pixels when the window is maximized.
#
# Cheatsheet:
#  "HotImage"      -> prelight
#  "NormalImage"   -> active
#  "PressedImage"  -> pressed
#  "DisabledImage" -> inactive
#
# Most of the buttons in the Metacity theme are 20x18 PNGs; $(BTNBASE) is 20x22

# Close button

close-prelight.xpm: $(MSRCDIR)/DWMWindow_CloseButton.Active_HotImage.png $(BTNBASE)
	composite -geometry +0+2 $+ +dither $@
close-pressed.xpm: $(MSRCDIR)/DWMWindow_CloseButton.Active_PressedImage.png $(BTNBASE)
	composite -geometry +0+2 $+ +dither $@
close-active.xpm: $(MSRCDIR)/DWMWindow_CloseButton.Active_NormalImage.png $(BTNBASE)
	composite -geometry +0+2 $+ +dither $@
close-inactive.xpm: $(MSRCDIR)/DWMWindow_CloseButton.Active_DisabledImage.png $(BTNBASE)
	composite -geometry +0+2 $+ +dither $@


# Maximize button

maximize-prelight.xpm: $(MSRCDIR)/DWMWindow_MaximizeButton.Active_HotImage.png $(BTNBASE)
	composite -geometry +0+2 $+ +dither $@
maximize-pressed.xpm: $(MSRCDIR)/DWMWindow_MaximizeButton.Active_PressedImage.png $(BTNBASE)
	composite -geometry +0+2 $+ +dither $@
maximize-active.xpm: $(MSRCDIR)/DWMWindow_MaximizeButton.Active_NormalImage.png $(BTNBASE)
	composite -geometry +0+2 $+ +dither $@
maximize-inactive.xpm: $(MSRCDIR)/DWMWindow_MaximizeButton.Active_DisabledImage.png $(BTNBASE)
	composite -geometry +0+2 $+ +dither $@


# Stick button. Use the UnMaximize once from the Metacity theme, since Xfwm
# uses the same image in both maximization states.

stick-prelight.xpm: $(MSRCDIR)/DWMWindow_UnMaximizeButton.Active_HotImage.png $(BTNBASE)
	composite -geometry +0+2 $+ +dither $@
stick-pressed.xpm: $(MSRCDIR)/DWMWindow_UnMaximizeButton.Active_PressedImage.png $(BTNBASE)
	composite -geometry +0+2 $+ +dither $@
stick-active.xpm: $(MSRCDIR)/DWMWindow_UnMaximizeButton.Active_NormalImage.png $(BTNBASE)
	composite -geometry +0+2 $+ +dither $@
stick-inactive.xpm: $(MSRCDIR)/DWMWindow_UnMaximizeButton.Active_DisabledImage.png $(BTNBASE)
	composite -geometry +0+2 $+ +dither $@


# Hide button (Minimize)

hide-prelight.xpm: $(MSRCDIR)/DWMWindow_MinimizeButton.Active_HotImage.png $(BTNBASE)
	composite -geometry +0+2 $+ +dither $@
hide-pressed.xpm: $(MSRCDIR)/DWMWindow_MinimizeButton.Active_PressedImage.png $(BTNBASE)
	composite -geometry +0+2 $+ +dither $@
hide-active.xpm: $(MSRCDIR)/DWMWindow_MinimizeButton.Active_NormalImage.png $(BTNBASE)
	composite -geometry +0+2 $+ +dither $@
hide-inactive.xpm: $(MSRCDIR)/DWMWindow_MinimizeButton.Active_DisabledImage.png $(BTNBASE)
	composite -geometry +0+2 $+ +dither $@


# Shade button (Minimize again, shifted vertically)

shade-prelight.xpm: $(MSRCDIR)/DWMWindow_MinimizeButton.Active_HotImage.png $(BTNBASE)
	composite -geometry +0-6 $+ +dither $@
shade-pressed.xpm: $(MSRCDIR)/DWMWindow_MinimizeButton.Active_PressedImage.png $(BTNBASE)
	composite -geometry +0-6 $+ +dither $@
shade-active.xpm: $(MSRCDIR)/DWMWindow_MinimizeButton.Active_NormalImage.png $(BTNBASE)
	composite -geometry +0-6 $+ +dither $@
shade-inactive.xpm: $(MSRCDIR)/DWMWindow_MinimizeButton.Active_DisabledImage.png $(BTNBASE)
	composite -geometry +0-6 $+ +dither $@



# Menu button
# This uses 16x21 nominal-pixel SVG sources

menu-prelight.xpm: $(MSRCDIR)/menu-focus.svg $(BTNBASE)
	convert $(BTNBASE) -background none $< -geometry +2-1 -composite +dither $@
menu-pressed.xpm: $(MSRCDIR)/menu-pressed.svg $(BTNBASE)
	convert $(BTNBASE) -background none $< -geometry +2-1 -composite +dither $@
menu-active.xpm: $(MSRCDIR)/menu-focus-normal.svg $(BTNBASE)
	convert $(BTNBASE) -background none $< -geometry +2-1 -composite +dither $@
menu-inactive.xpm: $(MSRCDIR)/menu-focus-none.svg $(BTNBASE)
	convert $(BTNBASE) -background none $< -geometry +2-1 -composite +dither $@


