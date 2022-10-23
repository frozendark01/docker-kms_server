# vlmcsd is a replacement for Microsoft's KMS server.
<pre>vlmcsd is not a one-click activation or crack tool intended to activate illegal copies of software (Windows, Office, Project, Visio)</pre>
**Docker based in Alpine OS with vlmcsd compiled from "source" (Wind4 GitHub) Server Usage:**
 <pre>docker run -d -p 1688:1688 --restart=always --name vlmcsd fr0zendark/kmsserver</pre>
 **or Docker Compose**
 <pre>
 version: '3.3'
 services:
    kmsserver:
        ports:
            - '1688:1688'
        restart: always
        container_name: vlmcsd
        image: fr0zendark/kmsserver
        </pre>
**To view docker log:**
<br />
**Now (thanks to embii74) vlmcsd process send logs to docker.**

<pre>$ docker logs vlmcsd (change 'vlmcsd' with the docker's name)</pre>

**Client Windows**
<pre>
slmgr.vbs -upk
slmgr.vbs -ipk XXXXX-XXXXX-XXXXX-XXXXX-XXXXX
slmgr.vbs -skms DOCKER_IP
slmgr.vbs -ato
slmgr.vbs -dlv
</pre>

**Office x86**
<pre>
cd \Program Files (x86)\Microsoft Office\Office16
cscript ospp.vbs /sethst:DOCKER_IP
cscript ospp.vbs /inpkey:xxxxx-xxxxx-xxxxx-xxxxx-xxxxx
cscript ospp.vbs /act
cscript ospp.vbs /dstatusall
</pre>

**Office x86_64**
<pre>
cd \Program Files\Microsoft Office\Office16
cscript ospp.vbs /sethst:DOCKER_IP
cscript ospp.vbs /inpkey:xxxxx-xxxxx-xxxxx-xxxxx-xxxxx
cscript ospp.vbs /act
cscript ospp.vbs /dstatusall
</pre>

**GVLK keys**
<pre>
Windows: https://docs.microsoft.com/en-us/windows-server/get-started/kmsclientkeys
Office 2013: https://technet.microsoft.com/en-us/library/dn385360.aspx
Office 2016 & 2019: https://technet.microsoft.com/en-us/library/dn385360(v=office.16).aspx
</pre>
**Docker Link**
<pre>https://hub.docker.com/r/fr0zendark/kmsserver/</pre>

