# swat-yars

[swat](https://github.com/melezhik/swat) black box testing for yars restapi


# install

    carton

# run tests

    # run tests against default host - 127.0.0.1:9001

    carton exec swat


    vagrant@Debian-jessie-amd64-netboot:~/projects/swat-yars$ carton exec swat
    /home/vagrant/.swat/.cache/939/prove/status/00.GET.t ...............
    ok 1 - GET localhost:9001/status succeeded
    # response saved to /home/vagrant/.swat/.cache/939/prove/UO6bFilQB9
    ok 2 - output match '200 OK'
    ok 3 - output match /{.*}/
    ok 4 - '{"app_name":"Yars","server_version":"1.1' match /"server_version":"(\S+?)"/
    ok 5 - server_version not null: 1.15
    1..5
    ok
    /home/vagrant/.swat/.cache/939/prove/virtual/upload-file/00.GET.t ..
    ok 1 - DELETE localhost:9001/file/test_file1/d41d8cd98f00b204e9800998ecf8427e succeeded
    # response saved to /home/vagrant/.swat/.cache/939/prove/Xdu3_c5v_1
    ok 2 - output match /(200 OK|404 Not Found)/
    ok 3 - PUT localhost:9001/file/test_file1/d41d8cd98f00b204e9800998ecf8427e succeeded
    # response saved to /home/vagrant/.swat/.cache/939/prove/RlgXyYvbqo
    ok 4 - output match '201 Created'
    ok 5 - [b] output match ':blank_line'
    ok 6 - [b] output match /^ok/
    ok 7 - response is already set
    # response saved to /home/vagrant/.swat/.cache/939/prove/gEvcLjFqkU
    ok 8 - output match 'done'
    1..8
    ok
    All tests successful.
    Files=2, Tests=13,  0 wallclock secs ( 0.01 usr  0.02 sys +  0.11 cusr  0.00 csys =  0.14 CPU)
    Result: PASS
    

# run tests against a dedicated host

    carton exec swat 192.168.0.1:9001

# author

Alexey Melezhik

# see also

* [https://github.com/melezhik/swat](https://github.com/melezhik/swat)










