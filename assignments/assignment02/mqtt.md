# Exploring MQTT QoS Levels

Experiment with QoS 0, 1, and 2.
Observe how message delivery changes based on QoS settings.

## Publisher_qos.py output

```
[15:29:47] DEBUG | Received PUBACK (Mid: 2025)
[15:29:47] PUBLISHED | msgid=2025
[15:29:47] DEBUG | Received PUBACK (Mid: 2026)
[15:29:47] PUBLISHED | msgid=2026
[15:29:47] DEBUG | Received PUBACK (Mid: 2027)
[15:29:47] PUBLISHED | msgid=2027
[15:29:47] DEBUG | Received PUBACK (Mid: 2028)
[15:29:47] PUBLISHED | msgid=2028
[15:29:50] DEBUG | Sending PUBLISH (d0, q1, r0, m2029), 'b'test/qos/6510301007/temperature'', ... (5 bytes)
[15:29:50] PUBLISH REQUESTED | SID=6510301007 | temperature=33.51 | QoS=1 | msgid=2029
[15:29:50] DEBUG | Sending PUBLISH (d0, q1, r0, m2030), 'b'test/qos/6510301007/humidity'', ... (5 bytes)
[15:29:50] PUBLISH REQUESTED | SID=6510301007 | humidity=42.68 | QoS=1 | msgid=2030
[15:29:50] DEBUG | Sending PUBLISH (d0, q1, r0, m2031), 'b'test/qos/6510301007/pressure'', ... (7 bytes)
[15:29:50] PUBLISH REQUESTED | SID=6510301007 | pressure=1009.35 | QoS=1 | msgid=2031
[15:29:50] DEBUG | Sending PUBLISH (d0, q1, r0, m2032), 'b'test/qos/6510301007/fan_speed'', ... (1 bytes)
[15:29:50] PUBLISH REQUESTED | SID=6510301007 | fan_speed=2 | QoS=1 | msgid=2032
[15:29:50] DEBUG | Received PUBACK (Mid: 2029)
[15:29:50] PUBLISHED | msgid=2029
[15:29:50] DEBUG | Received PUBACK (Mid: 2030)
[15:29:50] PUBLISHED | msgid=2030
[15:29:50] DEBUG | Received PUBACK (Mid: 2031)
[15:29:50] PUBLISHED | msgid=2031
[15:29:50] DEBUG | Received PUBACK (Mid: 2032)
[15:29:50] PUBLISHED | msgid=2032
```

## Subscriber_qos.py Output

```
Part 1

[15:25:20] DEBUG | Received PUBLISH (d0, q1, r0, m169), 'test/qos/6510301007/temperature', ...  (5 bytes)
[15:25:20] RECEIVED | temperature: 25.46 | QoS=1
[15:25:20] DEBUG | Sending PUBACK (Mid: 169)
[15:25:20] DEBUG | Received PUBLISH (d0, q1, r0, m170), 'test/qos/6510301007/humidity', ...  (5 bytes)
[15:25:20] RECEIVED | humidity: 56.88 | QoS=1
[15:25:20] DEBUG | Sending PUBACK (Mid: 170)
[15:25:20] DEBUG | Received PUBLISH (d0, q1, r0, m171), 'test/qos/6510301007/pressure', ...  (7 bytes)
[15:25:20] RECEIVED | pressure: 1014.56 | QoS=1
[15:25:20] DEBUG | Sending PUBACK (Mid: 171)
[15:25:20] DEBUG | Received PUBLISH (d0, q1, r0, m172), 'test/qos/6510301007/fan_speed', ...  (1 bytes)
[15:25:20] RECEIVED | fan_speed: 2 | QoS=1
[15:25:20] DEBUG | Sending PUBACK (Mid: 172)

Part 2
[15:27:19] DEBUG | Received PUBLISH (d0, q2, r0, m14), 'test/qos/6410301032/temperature', ...  (16 bytes)
[15:27:19] DEBUG | Sending PUBREC (Mid: 14)
[15:27:19] DEBUG | Received PUBREL (Mid: 14)
[15:27:19] RECEIVED | temperature: Smithhyyyyyyyyyy | QoS=2
[15:27:19] DEBUG | Sending PUBCOMP (Mid: 14)
[15:27:19] DEBUG | Received PUBLISH (d0, q1, r0, m15), 'test/qos/6510301002/temperature', ...  (5 bytes)
[15:27:19] RECEIVED | temperature: 26.67 | QoS=1
[15:27:19] DEBUG | Sending PUBACK (Mid: 15)
[15:27:20] DEBUG | Received PUBLISH (d0, q1, r0, m16), 'test/qos/6510301015/temperature', ...  (5 bytes)
[15:27:20] RECEIVED | temperature: 30.85 | QoS=1
[15:27:20] DEBUG | Sending PUBACK (Mid: 16)
[15:27:20] DEBUG | Received PUBLISH (d0, q1, r0, m17), 'test/qos/6510301007/temperature', ...  (5 bytes)
[15:27:20] RECEIVED | temperature: 30.97 | QoS=1
[15:27:20] DEBUG | Sending PUBACK (Mid: 17)
[15:27:20] DEBUG | Received PUBLISH (d0, q1, r0, m18), 'test/qos/6510301029/temperature', ...  (5 bytes)
[15:27:20] RECEIVED | temperature: 25.39 | QoS=1
[15:27:20] DEBUG | Sending PUBACK (Mid: 18)
[15:27:20] DEBUG | Received PUBLISH (d0, q1, r0, m19), 'test/qos/6510301023/temperature', ...  (5 bytes)
[15:27:20] RECEIVED | temperature: 30.26 | QoS=1
[15:27:20] DEBUG | Sending PUBACK (Mid: 19)
[15:27:20] DEBUG | Received PUBLISH (d0, q1, r0, m20), 'test/qos/6510301046/temperature', ...  (5 bytes)
[15:27:20] RECEIVED | temperature: 26.41 | QoS=1
[15:27:20] DEBUG | Sending PUBACK (Mid: 20)

Part 3
[15:28:26] DEBUG | Received PUBLISH (d0, q1, r0, m60), 'test/qos/6510301007/humidity', ...  (5 bytes)
[15:28:26] RECEIVED | humidity: 53.38 | QoS=1
[15:28:26] DEBUG | Sending PUBACK (Mid: 60)
[15:28:26] DEBUG | Received PUBLISH (d0, q1, r0, m61), 'test/qos/6510301029/pressure', ...  (6 bytes)
[15:28:26] RECEIVED | pressure: 1001.4 | QoS=1
[15:28:26] DEBUG | Sending PUBACK (Mid: 61)
[15:28:26] DEBUG | Received PUBLISH (d0, q1, r0, m62), 'test/qos/6510301007/pressure', ...  (7 bytes)
[15:28:26] RECEIVED | pressure: 1013.33 | QoS=1
[15:28:26] DEBUG | Sending PUBACK (Mid: 62)
[15:28:26] DEBUG | Received PUBLISH (d0, q1, r0, m63), 'test/qos/6510301029/fan_speed', ...  (1 bytes)
[15:28:26] RECEIVED | fan_speed: 0 | QoS=1
[15:28:26] DEBUG | Sending PUBACK (Mid: 63)
[15:28:26] DEBUG | Received PUBLISH (d0, q1, r0, m64), 'test/qos/6510301007/fan_speed', ...  (1 bytes)
[15:28:26] RECEIVED | fan_speed: 1 | QoS=1
[15:28:26] DEBUG | Sending PUBACK (Mid: 64)
[15:28:26] DEBUG | Received PUBLISH (d0, q2, r0, m65), 'test/qos/6510301044/temperature', ...  (6 bytes)
[15:28:26] DEBUG | Sending PUBREC (Mid: 65)
[15:28:26] DEBUG | Received PUBREL (Mid: 65)
[15:28:26] RECEIVED | temperature: Hi!!!! | QoS=2
[15:28:26] DEBUG | Sending PUBCOMP (Mid: 65)
[15:28:26] DEBUG | Received PUBLISH (d0, q1, r0, m66), 'test/qos/6510301046/temperature', ...  (5 bytes)
[15:28:26] RECEIVED | temperature: 31.06 | QoS=1
[15:28:26] DEBUG | Sending PUBACK (Mid: 66)
[15:28:26] DEBUG | Received PUBLISH (d0, q1, r0, m67), 'test/qos/6510301046/humidity', ...  (4 bytes)
[15:28:26] RECEIVED | humidity: 59.6 | QoS=1
[15:28:26] DEBUG | Sending PUBACK (Mid: 67)
[15:28:26] DEBUG | Received PUBLISH (d0, q1, r0, m68), 'test/qos/6510301046/pressure', ...  (7 bytes)
[15:28:26] RECEIVED | pressure: 1012.31 | QoS=1
[15:28:26] DEBUG | Sending PUBACK (Mid: 68)
[15:28:26] DEBUG | Received PUBLISH (d0, q1, r0, m69), 'test/qos/6510301046/fan_speed', ...  (1 bytes)
[15:28:26] RECEIVED | fan_speed: 3 | QoS=1
[15:28:26] DEBUG | Sending PUBACK (Mid: 69)
```