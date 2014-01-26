
backgrounddir = $(datadir)/themes/Adwaita/backgrounds
background_DATA = \
        adwaita-timed.xml \
        bright-day.jpg \
        good-night.jpg \
        morning.jpg


metadata_in_files = adwaita.xml.in
metadatadir = $(datadir)/gnome-background-properties
metadata_DATA = $(metadata_in_files:.xml.in=.xml)

adwaita.xml.in: adwaita.xml.in.in Makefile
	$(AM_V_GEN) $(SED) -e 's^\@datadir\@^$(datadir)^g' < $(srcdir)/adwaita.xml.in.in > adwaita.xml.in.tmp \
	&& mv adwaita.xml.in.tmp adwaita.xml.in

adwaita-timed.xml: adwaita-timed.xml.in Makefile
	$(AM_V_GEN) $(SED) -e 's^\@datadir\@^$(datadir)^g' < $(srcdir)/adwaita-timed.xml.in > adwaita-timed.xml.tmp \
	&& mv adwaita-timed.xml.tmp adwaita-timed.xml

@INTLTOOL_XML_RULE@

noinst_DATA = adwaita.xml.in
CLEANFILES = adwaita.xml adwaita.xml.in adwaita-timed.xml

EXTRA_DIST = $(background_DATA) adwaita.xml.in.in adwaita-timed.xml.in
