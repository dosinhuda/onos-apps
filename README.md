# onos-apps
1. install following https://hackmd.io/p/SkMbGhel-#/3/8
(run one time)
-> cd $onos
-> onos-buck-publish-local 
-> cd $onos/tools/package/archetypes
-> mvn clean install
-> cd ~/
2. cd MyApps
3. onos-create-app
4. run IJ (download and install: https://www.jetbrains.com/idea/download/#section=mac)
5. Import project: MyApps/[Folder]/pom.xlm
and modify to creat file .oar later:  
        <properties>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
        <onos.version>1.10.0-SNAPSHOT</onos.version>
        <onos.app.name>nctu.dosinhuda1.app</onos.app.name>
        <onos.app.origin>dosinhuda,community.</onos.app.origin>
6. File --> Import Setting: onos/tools/dev/idea-setting.jar
7. Compile source code without test
-> cd ~/MyApps/[Folder]
-> mvn clean install -DskipTests
8. Install app to a running ONOS
-> onos-app localhost install target/[file].oar
9. Only if reinstall needed
-> onos-app localhost reinstall nctu.dosinhuda1.app target/[file].oar
10. ex:sdn@sdn:~/onos/tools/package/archetypes/non3GPP_RAN-app$ onos-app 192.168.156.117 install target/non3GPP_RAN-app-1.10.0-SNAPSHOT.oar
11. sdn@sdn:~/onos/tools/package/archetypes/non3GPP_RAN-app$ onos-app 192.168.156.117 reinstall org.non3GPP_RAN.app target/non3GPP_RAN-app-1.10.0-SNAPSHOT.oar
12. To check: onos>apps -s
13. onos>apps
14. onos>apps -s -a
15. From MAC: MACs-MacBook-Air-2:dosinhuda_non3GPP.app mac$ mci && onos-app 192.168.156.117 reinstall NCTU.dosinhuda.app target/dosinhuda_non3GPP.app-1.0-SNAPSHOT.oar
16. Run onos on MAC: MACs-MacBook-Air-2:~ mac$ cd Applications/onos-1.10.0-rc2/bin/
17. sudo ./onos-service

