# WHAT its use for
  - it will upmix 2.0 to 5.1 channel using pipeware function and feature
  - plugin 
      - ladspa 
      - lv2
  - Surround Virtualizations from hesvui
  
# HOW TO INSTALL  
  - Artix Linux Support additional step
      - update RTKIT
      - Arch Repo      
  - make dir /usr/local/share/sbx4-sfx/filter/
  - get cmss_ent.wav and sbx100.wav from here https://sourceforge.net/projects/hesuvi/  
  - copy both cmss_ent.wav and sbx100.wav and put it in /usr/local/share/sbx4-sfx/filter/
  - sudo pacman -S ladspa lsp-plugins-ladspa  lsp-plugins-lv2
  - copy both folder pipewire and wireplumber into /home/\<user\>/.config/
  - then to use need choose one of this file soundblaster-upmix-with-cmss.conf.bak or soundblaster-upmix-with-sbx100.conf.bak 
  - then remove the ".bak" to activate

  - reload the pipewire and wireplumber
  - systemctl --user restart pipewire pipewire-pulse wireplumber


