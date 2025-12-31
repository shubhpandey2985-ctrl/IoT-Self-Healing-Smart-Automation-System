Flowchart TB
   subgraph Hardware_ Layer
      PS[Primary Sensor]
      BS[backup Sensor]
      CS[Current Sensor]
      ESP[ESP32 Controller]
      R[Relay Module]
      L[Load/Motor/Bulb]
  end

   subgraph Intelligence_ Layer
   SHA[System Health Analyzer]
   ARC[Autonomous Recovery Controller]
   HB[Heartbeat Monitor]
  end

   subgraph Monitoring_ layer
   MQTT[MQTT Broker]
   DB[telemetry database]
   UI[Resilience Monitor Dashboard]
  end

  PS-->ESP
  BS-->ESP
  CS-->ESP

  ESP-->SHA
  SHA-->ARC
  ARC-->R
  R-->L

   ARC-->HB
   ESP-->MQTT-->DB-->UI 