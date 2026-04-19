# WHAT its use for
  - it will upmix 2.0 to 5.1 channel using pipeware function and feature
  - plugin 
      - ladspa 
      - lv2
  - Surround Virtualizations from hesvui
  
# HOW TO INSTALL  
  - Artix Linux Support, additional step
      - update RTKIT it set sound processing to be more smooth
        ```
        i got this hint from chatgpt when i having problem on sound feel like delay and echoing
        
        restart are needed for the change
        sudo mkdir /etc/security/limits.d/
        sudo nano /etc/security/limits.d/99-audio-realtime.conf
        @audio - rtprio 98
        @audio - memlock unlimited
        @audio - nice -11
        ```
      - Arch Repo need for lsp ladspa
        ```
        sudo cp ./arch-mirrorlist /etc/pacman.d/ or copy any arch mirrorlist

        sudo nano /etc/pacman.conf
        # ARCH LINUX REPO
        [extra]
        Include = /etc/pacman.d/arch-mirrorlist
   
        you will encounter error pgp key that need to add, using this command to add the pgp key that shown in error
        sudo pacman-key --lsign-key <PGP_KEY_HERE>
   
        remember to comment out ths extra package after install if no more you need from it
        ```
      - Additional package need
        ```
        sudo pacman -S cmt swh-plugins
        ```
      - untested realtime group
        ```
        for me i also add this group, i dont know its required or not, i got this hint from chatgpt when i having problem on sound feel like delay and echoing
        sudo groupadd -r realtime
        sudo gpasswd -a $USER realtime
        ```
      - script for restart pipewire and plumber
        ```
        iam using dinit
        RESTART PIPEWIRE SCRIPT
        -------------------------------------
        #!/usr/bin/bash


        set -e

        echo "Stopping PipeWire stack..."
        dinitctl stop wireplumber || true
        dinitctl stop pipewire-pulse || true
        dinitctl stop pipewire || true

        sleep 2

        echo "Starting PipeWire stack..."

        dinitctl start pipewire
        dinitctl start pipewire-pulse
        dinitctl start wireplumber

        echo "Done."
        ```
  - make dir /usr/local/share/sbx4-sfx/filter/
  - get cmss_ent.wav and sbx100.wav from here https://sourceforge.net/projects/hesuvi/  
  - copy both cmss_ent.wav and sbx100.wav and put it in /usr/local/share/sbx4-sfx/filter/
  - sudo pacman -S ladspa lsp-plugins-ladspa  lsp-plugins-lv2
  - copy both folder pipewire and wireplumber into /home/\<user\>/.config/
  - then to use need choose one of this file soundblaster-upmix-with-cmss.conf.bak or soundblaster-upmix-with-sbx100.conf.bak 
  - then remove the ".bak" to activate

  - reload the pipewire and wireplumber
  - systemctl --user restart pipewire pipewire-pulse wireplumber


