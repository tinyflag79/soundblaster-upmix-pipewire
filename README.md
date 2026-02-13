# HOW TO INSTALL  
  make dir /usr/local/share/sbx4-sfx/filter/
  get cmss_ent.wav and sbx100.wav from here https://sourceforge.net/projects/hesuvi/  
  copy them put it in /usr/local/share/sbx4-sfx/filter/
  sudo pacman -S  lsp-plugins-ladspa  lsp-plugins-lv2
  copy both folder into /home/<user>/.config/
  then to use need choose one of this file soundblaster-upmix-with-cmss.conf.bak or soundblaster-upmix-with-sbx100.conf.bak 
  then remove the ".bak" to activate

  reload the pipewire and wireplumber
  systemctl --user restart pipewire pipewire-pulse wireplumber

  the audio-app-routing.conf to be reboot if it not works (i dont know how to reload the browser sink, the effective way is by rebooting)
