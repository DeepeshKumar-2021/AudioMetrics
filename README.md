# AudioMetrics

download freeswitch source from the latest git repository:
https://github.com/signalwire/freeswitch.git

Download code from AudioMetrics repository and merge the changes to freeswitch
do following configuration changes to freeswitch:

make below changes in conf/sip_profiles/internal.xml
<param name="enable-timer" value="false"/>

make following changes to conf/dialplan/default.xml
<action application="set" data="jitterbuffer_msec=60:200:20"/>
<action application="set" data="rtp_jitter_buffer_during_bridge=true"/>

you can refer files in AudioMetrics repository.

build freeswitch with below commands:
run below command in freeswitch source directory:
make && make install

restart freeswitch:
systemctl restart freeswitch.service

You can register extension using any open-source SIP client (Like Zoiper, X-lite etc) with
following details:
Username: <Extension>
Password: 12345
Domain: <instance IP address>
Available extensions are 1001, 1002, 1003 .
You may register any two extensions and call another extension.

once cal is done open freeswitch log file from location: /usr/local/freeswitch/freeswitch.log or find the exact location of logfile
search for below logs:
AUDIO QUALITY METRICS ==>



