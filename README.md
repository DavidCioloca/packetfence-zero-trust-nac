# Zero Trust NAC with PacketFence - Enterprise Security Review v3.1.1

This package is prepared for a cybersecurity competition review. It documents a wired NAC implementation using PacketFence, Samba AD, FreeRADIUS/Winbind and Extreme X435.

## Validated scenario

`test8021x -> PEAP-MSCHAPv2 -> Access-Accept -> Tunnel-Private-Group-Id=20 -> Extreme X435 port 2 in VLAN Users`

## v3.1 enterprise review additions

- explicit threat modeling: Rogue RADIUS, relay attacks, MAB spoofing;
- availability model: fail-closed vs controlled fail-open / ASU VLAN;
- end-to-end telemetry matrix: RADIUS -> switch -> endpoint;
- performance measurement protocol T0-T6;
- OPSEC versus auditability policy;
- detailed Control Plane / Data Plane diagram with ports.

## Known evidence gaps before final public demo

- Add `ipconfig /all` or `ip a` from the client after authentication, showing IP from VLAN 20.
- Add a pcap/timestamp-based latency measurement for EAPOL-Start to VLAN forwarding.

MAC address is published only as `e4:e7:49:xx:xx:xx` in narrative material; raw screenshots are annotated and secrets are redacted where visible.
