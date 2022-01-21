---
layout: page
title: Home Setups
subtitle: Network, Workbench, and IoT
permalink: /setups/
---

<div class="row">
  <div class="column">
    <h3>Network Setup</h3>
    <a href="#network"><img src="/img/projects/setups/server.png" alt="Network Setup" style="width:100%"></a>
  </div>

  <div class="column">
    <h3>Workbench Setup</h3>
    <a href="#workbench"><img src="/img/projects/setups/workbench.png" alt="Workbench Setup" style="width:100%"></a>
  </div>

  <div class="column">
    <h3>IoT Setup</h3>
    <a href="#iot"><img src="/img/projects/setups/iot.png" alt="IoT Setup" style="width:100%"></a>
  </div>
</div>

---

<h2 id="network">Network Setup (As of Jan 21st 2022)</h2>

<div class="row">
  <div class="column">
    <h3>TP-Link OC200 Omada<br>Hardware Controller</h3>
    <img src="/img/projects/setups/network/OC200.png" alt="TP-Link OC200 Omada Hardware Controller" style="width:100%">
     <p>
        Centralized Management<br>
        Up to 100 Omada Devices
     </p>
  </div>

  <div class="column">
    <h3>TP-Link ER605 Gigabit<br>VPN Router</h3>
    <img src="/img/projects/setups/network/ER605.png" alt="TP-Link ER605 Gigabit VPN Router" style="width:100%">
     <p>
        5 Gigabit Ports<br>
        High-Security VPN<br>
        Multi-WAN Load Balance
     </p>
  </div>
</div>

<div class="row">
  <div class="column">
    <h3>TP-Link TL-SG3210XHP-M2<br>Jetstream Switch</h3>
    <img src="/img/projects/setups/network/TL-SG3210XHP-M2.png" alt="TP-Link TL-SG3210XHP-M2 Jetstream Switch" style="width:100%">
     <p>
        8× 2.5 Gbps PoE+ Ports<br>
        2× 10 Gbps SFP+ Ports<br>
        240 W PoE Budget
     </p>
  </div>

  <div class="column">
    <h3>TP-Link EAP660 HD<br>AX3600 Access Point</h3>
    <img src="/img/projects/setups/network/EAP660-HD.png" alt="TP-Link EAP660 HD AX3600 Access Point" style="width:100%">
     <p>
        2.5G PoE+ Port<br>
        1148 Mbps on 2.4 GHz<br>
        2402 Mbps on 5 GHz
     </p>
  </div>
</div>

<div class="row">
  <div class="column">
    <h3>Smart Home Supervisor</h3>
    <img src="/img/projects/setups/network/rpi4B.png" alt="Smart Home Supervisor" style="width:100%">
  </div>

  <div class="column">
    <p style="text-align: left">
        <b>Raspberry Pi 4 Model B</b><br>
        Quad Core Cortex-A72 64-bit @ 1.5GHz<br>
        4GB LPDDR4-3200 SDRAM<br>
        Gigabit Ethernet with PoE HAT<br>
        2.5" 240GB SATA 3 Boot SSD<br>
        <br>
        <b>Nortek HUSBZB-1 Z-Wave/Zigbee Hub</b>
    </p>
  </div>

  <div class="column">
    <p style="text-align:left; vertical-align:top">
        <b>Home Assistant OS 7.1</b><br><br>
        <b>Add-on</b><br>
        ESPHome<br>
        Mosquitto MQTT Broker<br>
        Samba Backup & Share<br>
        Z-Wave JS Network Controller<br><br>
        <b>Integration</b><br>
        HACS<br>
        Font Awesome<br>
        HA TP-Link Omada
    </p>
  </div>
</div>

<div class="row">
  <div class="column">
    <h3>Light-load Docker<br>Container Machine</h3>
    <img src="/img/projects/setups/network/rpi3B.png" alt="Light-load Docker Container Machine" style="width:100%">
  </div>

  <div class="column">
    <p style="text-align: left">
        <b>Raspberry Pi 3 Model B</b><br>
        Quad Core BCM2837 64bit @ 1.2GHz<br>
        1GB LPDDR2 SDRAM<br>
        100Megabit Ethernet<br>
        64GB SD Card<br>
    </p>
  </div>

  <div class="column">
    <p style="text-align:left; vertical-align:top">
        <b>Raspbian GNU/Linux 11 (bullseye)</b><br><br>
        <b>Container</b><br>
        <a href="https://www.portainer.io/" target="_blank">Portainer Community Edition</a><br>
        <a href="https://heimdall.site/" target="_blank">heimdall</a><br>
        <a href="https://github.com/Tzahi12345/YoutubeDL-Material" target="_blank">YoutubeDL-Material</a><br>
        <a href="https://github.com/1activegeek/docker-airconnect" target="_blank">AirConnect</a><br>
        <a href="https://www.deluge-torrent.org/" target="_blank">Deluge</a><br>
        <a href="https://rxresu.me/" target="_blank">Reactive Resume</a><br>
    </p>
  </div>
</div>

<div class="row">
  <div class="column">
    <h3>High-load Service<br>and Storage Server</h3>
    <img src="/img/projects/setups/network/DS218plus.png" alt="High-load Service and Storage Server" style="width:100%">
  </div>

  <div class="column">
    <p style="text-align: left">
        <b>Synology DiskStation DS218+</b><br>
        Intel Celeron J3355 Dual Core @ 2 GHz<br>
        2GB(+4GB) DDR3L RAM<br>
        Gigabit Ethernet<br>
        2x 4TB WD Red NAS Hard Drive<br>
        <br>
        <b>Synology DX517 5 Bay Expansion Unit</b><br>
        3x 12TB WD 5400RPM 3.5" HDD<br>
        2x 8TB Seagate IronWolf NAS HDD
    </p>
  </div>

  <div class="column">
    <p style="text-align:left; vertical-align:top">
        <b>DiskStation Manager (DSM) 7.0</b><br><br>
        <b>Package</b><br>
        File Station (SMB)<br>
        Synology Photos<br>
        Surveillance Station<br>
        MariaDB 10<br>
        phpMyAdmin<br>
        <br>
        <b>Container</b><br>
        <a href="https://github.com/linuxserver/docker-calibre-web" target="_blank">Calibre-web</a><br>
        <a href="https://www.firefly-iii.org/" target="_blank">Firefly III</a><br>
        <a href="https://jellyfin.org/" target="_blank">Jellyfin</a><br>
        <a href="https://www.navidrome.org/" target="_blank">Navidrome</a><br>
        <a href="https://github.com/dani-garcia/vaultwarden" target="_blank">Vaultwarden</a><br>
    </p>
  </div>
</div>
