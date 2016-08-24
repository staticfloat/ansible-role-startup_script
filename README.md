## startup_script

Bare-bones Ansible role to make an `/etc/init.d/` startup script for whatever executable your heart may desire.

Usage goes something like this:
```
    - role: startup_script
      service_name: buildslave
      script_setup: "export PATH={{home.stdout}}/local/bin:{{home.stdout}}/local/sbin:$PATH\nexport LD_LIBRARY_PATH={{home.stdout}}/local/lib:{{home.stdout}}/local/lib64:$LD_LIBRARY_PATH"
      chdir: "{{home.stdout}}/buildbot/slave"
      daemon_name: "{{home.stdout}}/buildbot/sandbox/bin/buildslave"
      daemon_opts: "start --nodaemon"
```
