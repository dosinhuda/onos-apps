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

