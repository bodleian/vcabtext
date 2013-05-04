vcabtext
========

Django website for holding vocabularies and other text file formats
to create persistent URLS.


== Setup ==
The python script djsetup.py automates some of the setting up in the /opt folder.


=== Development setup ===

There are three stages.

==== Stage A: setup opt ====
1. You need to create the make the directories needed.
sudo ./djsetup -m

2. Change ownership of folders to your login.
sudo ./djsetup -f

==== Stage B: setup django ==== 
3. When in the vocabdj folder of this project the django sync works.
./manage.py syncdb

4. You can run the test server.
./manage.py runserver

OR
4a. Get your IP address. (eg. eth0... inet addr: ipaddress)
ifconfig

4b. Make test server available to subnet on port 7000
./manage.py runserver ipaddress:7000

==== Stage C: load dumped data. ==== 
5. If data has been 'dumped' in the fixtures folders you can load it.
./restore load
NOTE: if flatpages does not contain an item '/' you will get a 404 error n


=== Production setup ===
There is one stage. But the webserver still needs setting up.

==== Stage A: setup opt and sync latest git master====
1. sudo ./djsetup -s
