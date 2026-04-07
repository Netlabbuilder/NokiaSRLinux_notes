- To view interface report, probably for up interfaces, run `show interface`:
  
  ```
  --{ running }--[  ]--
  A:admin@leaf1# show interface
  ============================================================================================================================
  ethernet-1/1 is up, speed 25G, type None
    ethernet-1/1.0 is up
      Network-instances:
        * Name: default (default)
      Encapsulation   : null
      Type            : routed
      IPv4 addr    : 172.16.1.1/31 (static, preferred, primary)
  ----------------------------------------------------------------------------------------------------------------------------
  ethernet-1/2 is up, speed 25G, type None
    ethernet-1/2.0 is up
      Network-instances:
        * Name: default (default)
      Encapsulation   : null
      Type            : routed
      IPv4 addr    : 172.16.2.1/31 (static, preferred, primary)
  ----------------------------------------------------------------------------------------------------------------------------
  ethernet-1/3 is up, speed 25G, type None
  ----------------------------------------------------------------------------------------------------------------------------
  mgmt0 is up, speed 1G, type None
    mgmt0.0 is up
      Network-instances:
        * Name: mgmt (ip-vrf)
      Encapsulation   : null
      Type            : None
      IPv4 addr    : 172.20.20.7/24 (dhcp, preferred)
      IPv6 addr    : 3fff:172:20:20::7/64 (dhcp, preferred)
      IPv6 addr    : fe80::42:acff:fe14:1407/64 (link-layer, preferred)
  ----------------------------------------------------------------------------------------------------------------------------
  ============================================================================================================================
  Summary
    0 loopback interfaces configured
    3 ethernet interfaces are up
    1 management interfaces are up
    3 subinterfaces are up
  ============================================================================================================================
  
  --{ running }--[  ]--
  A:admin@leaf1#
  ```
- To view interface report for a specific interface, run one of the following commands:
  
  - `show interface <interface-name>`:
  
    ```
    A:admin@leaf1# show interface ethernet-1/1
    ============================================================================================================================
    ethernet-1/1 is up, speed 25G, type None
      ethernet-1/1.0 is up
        Network-instances:
          * Name: default (default)
        Encapsulation   : null
        Type            : routed
        IPv4 addr    : 172.16.1.1/31 (static, preferred, primary)
    ----------------------------------------------------------------------------------------------------------------------------
    ============================================================================================================================
  
    --{ running }--[  ]--
    A:admin@leaf1#
    ```
  - `show interface <interface-name> brief`:
    ```
    --{ running }--[  ]--
    A:admin@leaf1# show interface ethernet-1/1 brief
    +---------------------+-------------------+-------------------+-------------------+-------------------+-------------------+
    |        Port         |    Admin State    |    Oper State     |       Speed       |       Type        |    Description    |
    +=====================+===================+===================+===================+===================+===================+
    | ethernet-1/1        | enable            | up                | 25G               |                   | spine1-eth1/1     |
    +---------------------+-------------------+-------------------+-------------------+-------------------+-------------------+
    ```
  - `show interface <interface-name> all`:
    ```
      --{ running }--[  ]--
      A:admin@leaf1# show interface ethernet-1/1 all
      ============================================================================================================================
      ethernet-1/1 is up, speed 25G, type None
        ethernet-1/1.0 is up
          Network-instances:
            * Name: default (default)
          Encapsulation   : null
          Type            : routed
          IPv4 addr    : 172.16.1.1/31 (static, preferred, primary)
      ----------------------------------------------------------------------------------------------------------------------------
      ============================================================================================================================
    ```
  - `show interface <interface-name> detail`:
    ```
    --{ running }--[  ]--
    A:admin@leaf1# show interface ethernet-1/1 detail
    ============================================================================================================================
    Interface: ethernet-1/1
    ----------------------------------------------------------------------------------------------------------------------------
      Description         : spine1-eth1/1
      Oper state          : up
      Down reason         : N/A
      Last change         : 47m13s ago, 1 flaps since last clear
      Speed               : 25G
      Flow control        : Rx is disabled
      Loopback mode       : none
      MTU                 : 9232
      VLAN tagging        : false
      VLAN TPID           : TPID_0X8100
      MAC address         : 1A:97:04:FF:00:01
      Last stats clear    : never
      Breakout mode       : false
    ----------------------------------------------------------------------------------------------------------------------------
    L2CP transparency rule for ethernet-1/1
    ----------------------------------------------------------------------------------------------------------------------------
      Lldp              : trap-to-cpu-untagged
      Lacp              : trap-to-cpu-untagged
      xStp              : drop-tagged-and-untagged
      Ptp               : drop-tagged-and-untagged
      Non-specified l2cp: false
    ----------------------------------------------------------------------------------------------------------------------------
    Traffic statistics for ethernet-1/1
    ----------------------------------------------------------------------------------------------------------------------------
           counter         Rx      Tx
      Octets              18946   20394
      Unicast packets     8       7
      Broadcast packets   5       6
      Multicast packets   95      96
      Errored packets     0       0
      FCS error packets   0       N/A
      MAC pause frames    0       0
      Oversize frames     0       N/A
      Jabber frames       0       N/A
      Fragment frames     0       N/A
      CRC errors          0       N/A
    ----------------------------------------------------------------------------------------------------------------------------
    Traffic rate statistics for ethernet-1/1
    ----------------------------------------------------------------------------------------------------------------------------
        units     Rx   Tx
      kbps rate   0    0
    ----------------------------------------------------------------------------------------------------------------------------
    Frame length statistics for ethernet-1/1
    ----------------------------------------------------------------------------------------------------------------------------
      Frame length(Octets)   Rx   Tx
      64 bytes               6    6
      65-127 bytes           13   7
      128-255 bytes          95   96
      256-511 bytes          0    0
      512-1023 bytes         0    0
      1024-1518 bytes        0    0
      1519+ bytes            0    0
    ----------------------------------------------------------------------------------------------------------------------------
    Transceiver detail for ethernet-1/1
    ----------------------------------------------------------------------------------------------------------------------------
      Status          : Transceiver state is down
      Oper down reason: not-present
    ============================================================================================================================
      Subinterface: ethernet-1/1.0
    ----------------------------------------------------------------------------------------------------------------------------
      Description     : <None>
      Network-instance: default
      Type            : routed
      Oper state      : up
      Down reason     : N/A
      Last change     : 47m12s ago
      Encapsulation   : null
      IP MTU          : 1500
      Last stats clear: never
      IPv4 addr    : 172.16.1.1/31 (static, preferred, primary)
    ----------------------------------------------------------------------------------------------------------------------------
    ARP/ND summary for ethernet-1/1.0
    ----------------------------------------------------------------------------------------------------------------------------
      IPv4 ARP entries : 0 static, 1 dynamic
      IPv6 ND  entries : 0 static, 0 dynamic
    ----------------------------------------------------------------------------------------------------------------------------
    Traffic statistics for ethernet-1/1.0
    ----------------------------------------------------------------------------------------------------------------------------
         Statistics        Rx    Tx
      Packets             13     7
      Octets              1106   686
      Discarded packets   13     0
      Forwarded packets   0      0
      Forwarded octets    0      0
      CPM packets         -      7
      CPM octets          -      686
    ----------------------------------------------------------------------------------------------------------------------------
    IPv4 Traffic statistics for ethernet-1/1.0
    ----------------------------------------------------------------------------------------------------------------------------
    ----------------------------------------------------------------------------------------------------------------------------
    IPv6 Traffic statistics for ethernet-1/1.0
    ----------------------------------------------------------------------------------------------------------------------------
    ============================================================================================================================
    ============================================================================================================================
    
    --{ running }--[  ]--
    A:admin@leaf1#
    ```
