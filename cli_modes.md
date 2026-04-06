SR Linux CLI has three main modes: `running`, `candidate` and `state`:
- `running` mode

  When a user logs into SR Linux, they start in this mode.

  Users can use operational and show commands, view configuration and perform actions via `/tools` commands, but cannot perform any configuration changes.

  ```
  --{ running }--[  ]--
  A:admin@leaf1#
  ```
- `candidate` mode

  Users can perform configuration changes in the candidate datastore.
  ```
  --{ candidate shared default }--[  ]--
  A:admin@leaf1#
  ```
- `state` mode

  This mode is similar to the `running` mode as users can view configuration, execute operational and show commands.
  But in addition to that, users can also view the state information, that is the values that are non-configurable, but are calculated by the system.

  ```
  --{ state }--[  ]--
  A:admin@leaf1#
  ```
- To change CLI modes, type `enter <target-mode>` anywhere in the CLI will change the current mode to the target mode:
  ```
  --{ running }--[  ]--
  A:admin@leaf1# enter candidate
  
  
  --{ candidate shared default }--[  ]--
  A:admin@leaf1# enter state
  
  
  --{ state }--[  ]--
  A:admin@leaf1# enter running
  
  
  --{ running }--[  ]--
  A:admin@leaf1#
  ```
