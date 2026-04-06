The `info` command displays configuration and state information, run this command in candidate or running mode:

- From the root context displays the entire configuration or the configuration for a specified context.

- From within a context limits the display to the configuration under that context.

Examples:
- To display the entire configuration, run `info` from the root context:

  ```
  --{ running }--[  ]--
  A:admin@leaf1# info
      !!! ACL rules allowing incoming tcp/57411 for the eda-discovery grpc server
      acl {
          acl-filter cpm type ipv4 {
              statistics-per-entry true
              entry 10 {
                  description "Accept incoming ICMP unreachable messages"
                  match {
                      ipv4 {
                          protocol icmp
                          icmp {
                              type dest-unreachable
                          }
                      }
                  }
                  action {
                      accept {
                          rate-limit {
                              system-cpu-policer icmp
                          }
                      }
                  }
              }
    ...
    ...
    interface mgmt0 {
        admin-state enable
        subinterface 0 {
            admin-state enable
            ipv4 {
                admin-state enable
                dhcp-client {
                }
            }
            ipv6 {
                admin-state enable
                dhcp-client {
                }
            }
        }
    }
  
  
  --{ running }--[  ]--
  A:admin@leaf1#
  ```
- To display the configuration for a specific context, enter `info` and specify the context:
  ```
  --{ running }--[  ]--
  A:admin@leaf1# info interface ethernet-1/1
      description spine1-eth1/1
      admin-state enable
  
  
  --{ running }--[  ]--
  A:admin@leaf1#
  ```
  or
  ```
  --{ running }--[  ]--
  A:admin@leaf1# interface ethernet-1/1
  
  
  --{ running }--[ interface ethernet-1/1 ]--
  A:admin@leaf1# info
      description spine1-eth1/1
      admin-state enable
  
  
  --{ running }--[ interface ethernet-1/1 ]--
  A:admin@leaf1#
  ```
