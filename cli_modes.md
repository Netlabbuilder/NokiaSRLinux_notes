SR Linux CLI has three main modes: `running`, `candidate` and `state`:
- `running` mode - when a user logs into SR Linux, they start in this mode.

  Users can use operational and show commands, view configuration and perform actions via `/tools` commands, but cannot perform any configuration changes.

  ```
  --{ running }--[  ]--
  A:admin@leaf1#
  ```
- `candidate` mode - Users can perform configuration changes in the candidate datastore.
  ```
  --{ candidate shared default }--[  ]--
  A:admin@leaf1#
  ```
