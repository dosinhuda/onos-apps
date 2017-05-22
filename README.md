# onos-apps
1. install following https://hackmd.io/p/SkMbGhel-#/3/8
1.1. MACs-MacBook-Air-2:~ mac$ export JAVA_HOME=$(/usr/libexec/java_home -v 1.8)
1.2. MACs-MacBook-Air-2:~ mac$ export ONOS_ROOT="/Users/$USER/onos"
1.3. MACs-MacBook-Air-2:~ mac$ source $ONOS_ROOT/tools/dev/bash_profile
1.4. MACs-MacBook-Air-2:~ mac$ . ~/.bash_profile
1.5. cd $onos
1.6. onos-buck-publish-local 
1.7. cd onos/tools/package/archetypes
1.8. mvn clean install
1.9  cd ~/
2. cd MyApps 
3. onos-create-app
3.1. Define value for property 'groupId': nctu.dosinhuda
3.2. Define value for property 'artifactId': dosinhuda.non3GPP.app
3.3. Define value for property 'version' 1.0-SNAPSHOT: : 1.10.0.rc2
3.4. Define value for property 'package' nctu.dosinhuda: : nctu.dosinhuda.non3GPP
3.5. MACs-MacBook-Air-2:MyApps mac$ cd dosinhuda.non3GPP.app/
3.6. MACs-MacBook-Air-2:dosinhuda.non3GPP.app mac$ sudo gedit pom.xml 
3.7. edit properties: <onos.app.name>nctu.dosinhuda.non3GPP.app</onos.app.name>
3.8.  <onos.app.origin>non3GPP, Community.</onos.app.origin>
3.9. mvn clean install
3.10. MACs-MacBook-Air-2:dosinhuda.non3GPP.app mac$ onos-app 192.168.0.5 install target/dosinhuda.non3GPP.app-1.10.0.rc2.oar
3.11. Edit program and rebuit: MACs-MacBook-Air-2:dosinhuda.non3GPP.app mac$ mvn clean install
3.12. MACs-MacBook-Air-2:dosinhuda.non3GPP.app mac$ onos-app 192.168.0.5 reinstall nctu.dosinhuda.non3GPP.app target/dosinhuda.non3GPP.app-1.10.0.rc2.oar 
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

