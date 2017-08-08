ansible-role-cfg-accounts
=========================

Todo

#### Variables for no custom users:


    local_users: {}
    local_groups: {}
    deleted_local_users:
      - user1
      - user2
    deleted_local_groups:
      - group1
      - group2
      - group3


#### Variables for having specific users on systems:


    deleted_local_groups: []
    deleted_local_users: []
    local_users:
      user1:
        firstname: first
        lastname: last
        pubkeys:
          - 'ssh-rsa key1 comment'
          - 'ssh-dsa key2 comment'

        (optional:)
        comment: "blablabla"            # default is "ANSIBLE MANGED USER"
        createhome: no                  # default is yes
        group: existing-maingroup       # default creates <username>
        groups: []                      # list of other groups to put user in
        home: /path/to/home/dir         # default is /home/<username>
        home_user: username             # default is <username>
        home_group: group               # default is <group>
        home_mode: '0700'               # default is 0770
        shell: '/bin/zsh'               # default is bash
        system: yes                     # default is no
        uid: 2000                       # custom uid

      user2:
        ...

    local_groups:
      group1:
        gid: 3900
        members:
          - user1
          - user2

      group2:
        ...

