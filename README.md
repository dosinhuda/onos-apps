# onos-apps
1. install following https://hackmd.io/p/SkMbGhel-#/3/8
2. MACs-MacBook-Air-2:~ mac$ export JAVA_HOME=$(/usr/libexec/java_home -v 1.8)
3. MACs-MacBook-Air-2:~ mac$ export ONOS_ROOT="/Users/$USER/onos"
4. MACs-MacBook-Air-2:~ mac$ source $ONOS_ROOT/tools/dev/bash_profile
5. MACs-MacBook-Air-2:~ mac$ . ~/.bash_profile
6. cd $onos
7. onos-buck-publish-local 
8. cd onos/tools/package/archetypes
9. mvn clean install -DskipTests
10.  cd ~/
11. cd MyApps 
12. onos-create-app
13. Define value for property 'groupId': nctu.dosinhuda
14. Define value for property 'artifactId': dosinhuda.non3GPP.app
15. Define value for property 'version' 1.0-SNAPSHOT: : 1.10.0.rc2
16. Define value for property 'package' nctu.dosinhuda: : nctu.dosinhuda.non3GPP
17. MACs-MacBook-Air-2:MyApps mac$ cd dosinhuda.non3GPP.app/
18. MACs-MacBook-Air-2:dosinhuda.non3GPP.app mac$ sudo gedit pom.xml 
19. edit properties: <onos.app.name>nctu.dosinhuda.non3GPP.app</onos.app.name>
20.  <onos.app.origin>non3GPP, Community.</onos.app.origin>
21. mvn clean install -DskipTests
22. MACs-MacBook-Air-2:dosinhuda.non3GPP.app mac$ onos-app 192.168.0.5 install target/dosinhuda.non3GPP.app-1.10.0.rc2.oar (or install! to activate)
23. Edit program and rebuit: MACs-MacBook-Air-2:dosinhuda.non3GPP.app mac$ mvn clean install
24. MACs-MacBook-Air-2:dosinhuda.non3GPP.app mac$ onos-app 192.168.0.5 reinstall nctu.dosinhuda.non3GPP.app target/dosinhuda.non3GPP.app-1.10.0.rc2.oar (or reinstall! to activate)
25. run IJ (download and install: https://www.jetbrains.com/idea/download/#section=mac)
26. Import project: MyApps/[Folder]/pom.xlm
27. File --> Import Setting: onos/tools/dev/idea-setting.jar
28. onos>apps
29. onos>apps -s -a
30. Run onos on MAC: MACs-MacBook-Air-2:~ mac$ cd Applications/onos-1.10.0-rc2/bin/
31. sudo ./onos-service
32. onos>flows : to check flows added to switch from apps
33. onos>summary
34. onos> masters
35. nos> flows | grep ICMP
36. nos> flows | grep ARP
37. onos> apps | grep ICMP
38. onos> apps | grep ARP
