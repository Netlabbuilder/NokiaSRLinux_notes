The plus sign (+) in the prompt indicates that the running configuration differs from the startup configuration.

After you enter the `save startup` command, the running configuration is synchronized with the startup configuration, and the plus sign is removed from the prompt.

```
--{ + running }--[  ]--
A:admin@leaf1# save startup
/system:
    Saved current running configuration as initial (startup) configuration '/etc/opt/srlinux/config.json'



--{ running }--[  ]--
A:admin@leaf1#
```
