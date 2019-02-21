# RAK831-LoRaGateway-RPi
The RAK831 gateway is based on the latest SX1301 driver [lora_gateway](https://github.com/Lora-net/lora_gateway) v5.0.1 and semtech [packet_forwarder](https://github.com/Lora-net/packet_forwarder) v4.0.1  


##	Installation procedure

step 1 : Download and install [Raspbian LITE version](https://www.raspberrypi.org/downloads/raspbian/)

step 2 : Clone the installer and start the installation

      $ git clone https://github.com/robertlie/RAK831-LoRaGateway-RPi ~/rak831-loragateway
      $ cd ~/rak831-loragateway
      $ sudo ./install.sh

Step 3 : You must know which frequency plan to use in your country.<br>
     See the list of frequency plans by country list:<br>
     https://www.thethingsnetwork.org/docs/lorawan/frequencies-by-country.html<br>
     The frequency plans can be found at:<br>
     https://www.thethingsnetwork.org/docs/lorawan/frequency-plans.html<br>
     If you know the frequency plan, look at the table and find the corresponding Region.

     | Region | Frequency Plan |
     |--------|----------------|
     | AS1    | AS920-923      |
     | AS2    | AS923-925      |
     | AU     | AU915-928      |
     | CN     | CN470-510      |
     | EU     | EU863-870      |
     | IN     | IN865-867      |
     | KR     | KR920-923      |
     | RU     | -              |
     | US     | US902-928      |

step 4 : Next you will see some messages. Just hit the Enter key to keep default or enter your information if you want.

      Hostname [ttn-gateway]:
      Region AS1, AS2, AU, CN, EU, IN, KR, RU, US [EU]:
      Latitude in degrees [0.0]
      Longitude in degrees [0.0]:
      Altitude in meters [0]

step 5 : This step is optional. By default GPS is disabled. If you want to use GPS:

      - Attach the GPS antenna.
        For better GPS results the antenna must be placed outside with a clear view of the sky.
        The antenna needs to have an open line of sight to the GPS satellites in the sky.
      - Next modify /opt/ttn-gateway/packet_forwarder/lora_pkt_fwd/local_conf.json and uncomment the following content:

        "gateway_conf": {
            :
            "gps_tty_path": "/dev/ttyAMA0",
            "fake_gps": false
            :
        }

        Watch out for the commas. The JSON file must be valid!
      - Reboot the gateway after file local_conf.json is modified.

step 6 : Now you have a running gateway after restart!
