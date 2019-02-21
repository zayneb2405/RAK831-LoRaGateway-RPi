The NN-global_conf.json files were copied from (Latest commit 551afce  on 14 Aug 2018):
https://github.com/TheThingsNetwork/gateway-conf

The following modifications were made to these files:

     - Set lbt_cfg.enable = false
     - Remove the "servers" parameter and its value. The servers parameter are not used by the Semtech lora_gateway and packet_forwarder.

NN refers to a specific region (AS1, AS2, AU, CN, EU, IN, KR, RU and US) where a specific frequency plan is used.
