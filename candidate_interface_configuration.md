- To enable IPv4 address-family on a routed interface (non-tagging or non-dot1q), run `interface <interface-id> subinterface 0 ipv4 admin-state enable`:
  
  ```
  A:admin@spine2# interface ethernet-1/1 subinterface 0 ipv4 admin-state enable
  ```
- To configure an IPv4 address on a routed interface (non-tagging or non-dot1q), run `interface <interface-id> subinterface 0 ipv4 address <ip-prefix>`:

  ```
  A:admin@spine2# interface ethernet-1/1 subinterface 0 ipv4 address 172.16.2.0/31
  ```

- To assign an interface to a `network-instance`, run `network-instance <name> interface <interface-id>`:
  
  ```
  A:admin@spine2# network-instance default interface ethernet-1/1.0
  ```
