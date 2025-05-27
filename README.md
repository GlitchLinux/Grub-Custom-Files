https://glitchlinux.wtf/grub_backup.tar.gz


https://glitchlinux.wtf/grub_backup_no_live_97MB.tar.gz



# All labels that look like "__LABEL__" are replaced by SED in
# /usr/bin/remastersys around lines 345-400.
# Translations in /usr/share/locale/pt_BR/LC_MESSAGES/remastersys.po

set default="0"
set timeout=10

function load_video {
    insmod vbe
    insmod vga
    insmod video_bochs
    insmod video_cirrus
}

loadfont /usr/share/grub/unicode.pf2

set gfxmode=640x480
load_video
insmod gfxterm
set locale_dir=/boot/grub/locale
set lang=C
insmod gettext
background_image -m stretch /boot/grub/grub.png
terminal_output gfxterm
insmod png
if background_image /boot/grub/grub.png; then
    true
else
    set menu_color_normal=cyan/blue
    set menu_color_highlight=white/blue
fi
