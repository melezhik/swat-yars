# swat-yars

[swat](https://github.com/melezhik/swat) black box testing for yars restapi


# install

    carton

# run tests

    # run tests against default host - 127.0.0.1:9001

    carton exec swat

# run tests against a dedicated host

    carton exec swat 192.168.0.1:9001

# a sample output

```
vagrant@Debian-jessie-amd64-netboot:~/projects/swat-yars$ carton  exec swat
/home/vagrant/.swat/.cache/2140/prove/virtual/upload-file/00.GET.t ..
ok 1 - DELETE localhost:9001/file/test_file1/cb54dd2ea05ec90327464b40d27c0d55 failed, still continue due to ignore_http_err set to 1
# response saved to /home/vagrant/.swat/.cache/2140/prove/xS_R1CkkyV
ok 2 - output match /(200 OK|404 Not Found)/
ok 3 - PUT localhost:9001/file/test_file1/cb54dd2ea05ec90327464b40d27c0d55 succeeded
# response saved to /home/vagrant/.swat/.cache/2140/prove/41PiaCoKsy
ok 4 - output match '201 Created'
ok 5 - [b] output match ':blank_line'
ok 6 - [b] output match /^ok/
ok 7 - GET localhost:9001/file/test_file1/cb54dd2ea05ec90327464b40d27c0d55 succeeded
# response saved to /home/vagrant/.swat/.cache/2140/prove/Nugdr8OVFY
ok 8 - output match '200 OK'
ok 9 - output match 'HELLO WORLD'
ok 10 - response is already set
# response saved to /home/vagrant/.swat/.cache/2140/prove/JmOSjUhJqy
ok 11 - output match 'done'
1..11
ok
/home/vagrant/.swat/.cache/2140/prove/00.GET.t ......................
ok 1 - GET localhost:9001/ succeeded
# response saved to /home/vagrant/.swat/.cache/2140/prove/ShPYS6F8mx
ok 2 - output match '200 OK'
ok 3 - output match 'welcome to Yars'
1..3
ok
/home/vagrant/.swat/.cache/2140/prove/status/00.GET.t ...............
ok 1 - GET localhost:9001/status succeeded
# response saved to /home/vagrant/.swat/.cache/2140/prove/Chaz1rg4VK
ok 2 - output match '200 OK'
ok 3 - output match /{.*}/
ok 4 - '{"server_hostname":"Debian-jessie-amd64-' match /"server_version":"(\S+?)"/
ok 5 - server_version not null: 1.15
1..5
ok
All tests successful.
Files=3, Tests=19,  2 wallclock secs ( 0.03 usr  0.00 sys +  0.22 cusr  0.01 csys =  0.26 CPU)
Result: PASS

```

# author

Alexey Melezhik

# see also

* [https://github.com/melezhik/swat](https://github.com/melezhik/swat)










