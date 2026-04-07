- Changes made during a configuration modification session do not take effect until a `commit` command is issued. Only use the `commit` command in candidate mode.
    - To apply the changes and remain in candidate mode, enter `commit stay`.

    - To apply the changes, exit candidate mode, and enter running mode, enter `commit now`.

    - To apply the changes, remain in candidate mode, and save the changes to the startup configuration, enter `commit stay save`.

    - To apply a comment to a `commit stay` or `save` operation, use the `comment` keyword and specify a comment.

- The plus sign (+) in the prompt indicates that the running configuration differs from the startup configuration.

  After you enter the `save startup` command, the running configuration is synchronized with the startup configuration, and the plus sign is removed from the prompt.

    ```
    --{ + running }--[  ]--
    A:admin@leaf1# save startup
    /system:
        Saved current running configuration as initial (startup) configuration '/etc/opt/srlinux/config.json'
    
    
    
    --{ running }--[  ]--
    A:admin@leaf1#
    ```
