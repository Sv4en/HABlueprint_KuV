# HA-Änderungen (Claude-Sitzung, Oktober 2026)

Zweck: KuV-Blueprint Ver.1.03, Umstellung der Geräte, Aufräumen von Home Assistant und Optimierung des FoH-Tasters im Jungszimmer.
Nur Home Assistant (über den ha02-MCP-Server) und dieses Repo. Nichts an svendocker, NAS oder anderen Sitzungen geändert.

## Blueprints
- `Enerverbrauch/KuV_03.yaml` gespeichert (Repo: `KuV_03.yaml`).
- 10 ungenutzte Blueprints gelöscht: FoH Taste 1 (2x), 2, 3, 4, KuV_02_alt, Latenz-Test, `homeassistant/confirmable_notification`, `motion_light`, `notify_leaving_zone`.

## Automationen
- Neu/geändert: `geschirrspuler_kuv_03`, `waschmaschine_kuv_03`, `trockner_kuv_03`, `backofen_kuv_03`, `waschmaschine_abschluss_meldung`, `waschmaschine_ist_fertig`, `foh_jungszimmer_4_fach_neu`, `foh_jungszimmer_4_fach_halten`, `waschmaschine_smartthings_auto_reload`, `jungs_zimmer_fenster_zu_erinnerung` (Alexa durch Telegram ersetzt).
- Gelöscht: alte KuV-02-Automationen (Geschirrspüler, Waschmaschine, Trockner, Backofen).

## Skripte
- `senic_dimmen_schleife` gelöscht.

## Helfer (neu)
- `input_number.waschmaschine_wasser_start`
- FoH Jungszimmer: `input_boolean.foh_jungs_dim_up`, `foh_jungs_hold`, `foh_jungs_was_on`, `foh_jungs_slide_aktiv`; `input_number.foh_jungs_taste1_t`, `foh_jungs_taste1_release_t`, `foh_jungs_taste2_t`, `foh_jungs_aus_t`.

## Dashboards
- `dashboard-test01`: Ansicht „ID4“ und zwei „ID4 Akku“-Kacheln entfernt.
- `dashboard-raume`: tote Karten entfernt, Carport-Kacheln auf `switch.carport_e1_2` und `switch.carport_e1_2_2` umgestellt.

## Entity-Registry
- Rund 330 verwaiste Einträge entfernt (Fritz!Box-Tracker und -Schalter, Alexa-Media-Lichter und -Sensoren, alte Plugs und Lichter, alte Geräte-Lichter von Waschmaschine, Trockner, Backofen, Geschirrspüler).
- Bewusst behalten: VW/ID.4/Zoe, Weihnachten/Baum, Pumpen, go-e, Vaillant, s10e-Wallbox, Rollo Bad.

## Sonstiges
- Label „Pumpe“ gelöscht.
- SmartThings-Integration einmal neu geladen (Waschmaschine lieferte keine Daten).
- Backup vor der Registry-Bereinigung: `faad56a3`.

## Offen
- Shelly 1 Mini Gen3 für `light.madchenzimmer` (Automation folgt nach Einbau).
- Dashboards: Infos, Verbrauch Haus, Küche-Tab, E3DC, Geraete an, Weihnachten, Rest von Test01.
- Gruppe 2: Flood-Sensor, Bad-Bewegungsmelder, `wc_motion`, Tradfri, Hue-Außenmelder.
- Spook-Reparaturen: Template „Leistung L1–L3“, Energy-Meldung, Orphaned Statistics, „Carport X4 offline“.
- HA-Neustart am Ende (Spook, HACS, `mcp_proxy`).
