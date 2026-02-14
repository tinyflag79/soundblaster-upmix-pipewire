# WHAT is used inside of conf
  - pipeware function and feature
  - plugin 
      - ladspa 
      - lv2
  - Surround Virtualizations from hesvui
  
# HOW TO INSTALL  

  - make dir /usr/local/share/sbx4-sfx/filter/
  - get cmss_ent.wav and sbx100.wav from here https://sourceforge.net/projects/hesuvi/  
  - copy both cmss_ent.wav and sbx100.wav and put it in /usr/local/share/sbx4-sfx/filter/
  - sudo pacman -S  lsp-plugins-ladspa  lsp-plugins-lv2
  - copy both folder pipewire and wireplumber into /home/\<user\>/.config/
  - then to use need choose one of this file soundblaster-upmix-with-cmss.conf.bak or soundblaster-upmix-with-sbx100.conf.bak 
  - then remove the ".bak" to activate

  - reload the pipewire and wireplumber
  - systemctl --user restart pipewire pipewire-pulse wireplumber

  - on first apply 99-audio-app-routing.conf some time its not routing the browser sink
  so need to reboot (i dont know how to reload the browser sink, the effective way is by rebooting)
