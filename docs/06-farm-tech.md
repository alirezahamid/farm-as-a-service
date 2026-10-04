# 06: Farm tech (finally, the bit you are good at)

You will want to automate everything. Wait. Do the job by hand for a season
first. Then you know which part is worth automating.

## Principles (read before you solder)

1. **Automation does not replace looking.** A sensor tells you the
   temperature. It does not tell you the hen is limping.
2. **Fail safe.** Decide what happens when the power, the Wi-Fi, or the
   battery dies. A valve should fail closed. A coop door should have a manual
   override.
3. **Never let animal welfare depend on one device.** Water and lock-up need
   a human check every day.
4. **The farm is a hostile environment.** Mud, rain, frost, UV, rats, and
   curious goats. Budget for waterproof boxes and for replacing things.
5. **Low tech wins often.** A float valve fills a trough with no code. A
   mechanical timer waters a bed with no cloud account.
6. **Local first.** Rural internet drops. Your system must work offline.

## Spreadsheets (the most useful farm software)

Start here. Paper works too.

Track:

- Sowing dates, planting dates, and harvest dates
- Harvest weights per crop
- Egg counts per day
- Every cost and every sale
- Weather notes, with first and last frost dates
- Animal records: births, deaths, treatments, and movements

Medicine and movement records for food animals are a legal duty in many
countries. Check your [country page](../countries/README.md).

After two years, your own data beats any book. It is specific to your soil
and your climate.

## Sensors (observability)

Useful things to measure:

| Measure | Why |
| --- | --- |
| Air temperature | Frost alerts. Greenhouse overheating. |
| Soil moisture | When to water. Readings are relative, so calibrate to your soil. |
| Soil temperature | When seeds will germinate. |
| Water tank level | Know before it runs dry. |
| Electric fence voltage | Know when the fence is down before the sheep do. |
| Door open or closed | Coop, gate, and feed store. |
| Hive weight | Shows nectar flow and winter stores without opening the hive. |

Hardware notes:

- **ESP32 boards with ESPHome** are a cheap way to build sensors that report
  to Home Assistant.
- **Capacitive soil moisture probes** last longer than resistive ones, which
  corrode.
- **Power:** a small solar panel and a battery covers most sensor nodes. Use
  deep sleep.
- **Range:** Wi-Fi rarely reaches the field. Look at LoRa for long range and
  low power. Zigbee works around buildings.

## Home Assistant (the control plane)

[Home Assistant](https://www.home-assistant.io/) is open source home
automation software. It runs locally on a small computer. It works well as a
farm dashboard.

Common uses:

- Frost alert to your phone when the temperature drops near zero
- Greenhouse vent or fan control by temperature
- Coop door status, and an alert if it is still open after dusk
- Tank level and pump control
- Irrigation schedules that skip rainy days

Keep the automations simple. You will debug them in the dark, in the rain.

## Irrigation automation (cron jobs for plants)

Build it in this order:

1. **A hose and your hand.** Learn how much water your soil needs.
2. **Drip line and a battery tap timer.** Cheap. Solves most of the problem.
3. **A controller with weather data.** [OpenSprinkler](https://opensprinkler.com/)
   is open source and can skip watering when it rains.
4. **Soil moisture feedback.** Water only when the soil is dry. This is the
   hardest step to get right.

Use valves that close when power is lost. Add a flow sensor or a daily time
limit, so a stuck valve cannot empty your tank.

## Cameras

- Useful for lambing and kidding sheds, hives, and gates.
- [Frigate](https://frigate.video/) is an open source video recorder with
  local object detection. It works with Home Assistant.
- A camera shows you the fox. It does not stop the fox.

## Connectivity (the last mile is a field)

- Test mobile signal at the actual spot, not at the gate.
- Options: 4G or 5G router with an outdoor antenna, satellite internet, or a
  point-to-point Wi-Fi link from the house.
- For sensors: LoRaWAN through [The Things Network](https://www.thethingsnetwork.org/)
  or your own gateway.

## Open source farm software

| Project | What it does |
| --- | --- |
| [farmOS](https://farmos.org/) | Farm records, mapping, and planning. Self-hosted. |
| [LiteFarm](https://www.litefarm.org/) | Farm management for small and diversified farms. |
| [Home Assistant](https://www.home-assistant.io/) | Automation, dashboards, and alerts. |
| [ESPHome](https://esphome.io/) | Firmware for DIY sensors, set up with YAML. Yes, more YAML. |
| [OpenSprinkler](https://opensprinkler.com/) | Open source irrigation controller. |
| [FarmBot](https://farm.bot/) | Open source CNC machine for a raised bed. Fun. Not cheap. |
| [QGIS](https://qgis.org/) | Mapping. Plan fields, fences, and water lines. |
| [Zigbee2MQTT](https://www.zigbee2mqtt.io/) | Use Zigbee sensors without a vendor hub. |
| [Frigate](https://frigate.video/) | Camera recording with local object detection. |

Know a good one? Add it with a pull request. Say if you have used it.

## Common mistakes

1. **Automating before understanding.** You encode your beginner mistakes.
2. **Indoor parts outdoors.** They last one winter.
3. **Cloud-only devices.** They stop when the internet does, or when the
   vendor does.
4. **No manual override.** You will need it on the worst day.
5. **Alert fatigue.** If every alert is noise, you will miss the real one.
6. **Building tech in place of farming.** It is the fun, familiar part. The
   weeds do not care about your dashboard.

## Sources

- Project websites linked above.
- <!-- TODO: needs source — real setups from contributors, with parts lists and costs -->
