# Spotfire-Admin

### Spotfire Server Upgrade
Tibco Spotfire Documentation
```https://docs.tibco.com/products/tibco-spotfire/```

Spotfire server installation & configuration manual 
```https://docs.tibco.com/pub/spotfire_server/latest/doc/html/TIB_sfire_server_tsas_admin_help/server/topics/installation.html```

System requirement 
```https://docs.tibco.com/pub/spotfire/general/sr/sr/topics/system_requirements_for_spotfire_products.html```

For any other document refer 
```https://docs.tibco.com/```

### Recommendations prior to upgrade 
1) Ensure the spotfire env is up & running.
2) Take a backup of existing/working spotfire database.
3) Download all installation media from ```https://edelivery.tibco.com```
4) Perform these upgrades on pre-prod env & test before prod deployments.

Note : The NTLM authentication method reuses the identity information associated with the user's current Windows session. 
1) Spotfire server front end port : 80
2) Backend registration port : 9080
3) Backend communication port : 9443 <br>
<img width="512" alt="Screenshot 2023-10-04 183630" src="https://github.com/Gurudutt-Goswami/Spotfire-Admin/assets/86184439/678041cb-4546-4efa-bd97-5d2b1c01ba20"><br>

Note : Open configuration tool for fresh installation.<br>
Upgrade tool can also be located under Spotfire server installation directory > Tools > Upgrade Folder 

File Location<Br>
<img width="526" alt="file location" src="https://github.com/Gurudutt-Goswami/Spotfire-Admin/assets/86184439/b42aeaa0-f2d9-4af2-96ae-563b89c9d9b3"><Br>
<img width="179" alt="database things" src="https://github.com/Gurudutt-Goswami/Spotfire-Admin/assets/86184439/7aa30dbb-592c-4c40-8900-a7fac09b9c03"><br>
<img width="533" alt="database things 2" src="https://github.com/Gurudutt-Goswami/Spotfire-Admin/assets/86184439/05a320fd-ade0-4702-b37d-35ea6b8cad71"><br>

If you select to take detail from previous database then it will take information from bootstrap file.

The upgrade process generally takes around 5 min , once it completes we should check whether we it has found any issues while upgrading. We can find this information right after the upgrade in the wizard only or in ```upgrade-issues.html``` file under ```warning/issues``` path.

Once the upgrade is done the next step is to deploy the client package 
1) Login to admin UI
2) Go to deployments & packages
3) Click on Add packges & browse client deployment kit & upload.
4) Click on Validate area to check any compatibility issue with the package.
5) Click on Save area.
Once its deployed try starting Spotfire client & change server port if required. Once it open up it will throw a pop to install/upgrade to your installed version.


### Install & Configure Spotfire Node manager
This node manager installations enables following things in Spotfire env.
1) web player services
2) Automation Services
3) Terr services

You can find the ```nm setup.exe``` file server setup files 
1) After accepting the license you need to set ports.
2) If the Spotfire server machine & this nm setup machine is same change the port numbers.
<img width="345" alt="node manager" src="https://github.com/Gurudutt-Goswami/Spotfire-Admin/assets/86184439/2dd43ea0-ff3f-48df-9c9f-eb1a67a3bb0e"> <br>
3) After that you need to define the server name (ie., its FQDN (full qualified domain name) or you can server ip. <Br>
<img width="502" alt="ports " src="https://github.com/Gurudutt-Goswami/Spotfire-Admin/assets/86184439/b67b7bd2-8a37-4205-9e2f-bf4affbe4839"> <br>
4) Make sure network names are correct & then click on install
<img width="680" alt="network names" src="https://github.com/Gurudutt-Goswami/Spotfire-Admin/assets/86184439/3a5dd81f-0024-4a45-b2d7-5f39224cbed6"><br>
5) If this is a nm upgrade then open upgrade tool or else for the fresh setup you can exit.<br>
<img width="484" alt="nm complete" src="https://github.com/Gurudutt-Goswami/Spotfire-Admin/assets/86184439/3694095d-cc65-4e01-80c4-a76bedd347a8"><br>
6) Start node manager service<Br>
7) Open Admin UI > Nodes & Services > Go to untrusted node tab (In this we will our recently installed nm)<br>
8) Select the node & click on trust.<br>
9) Now go to You Network > click on install new service<br>
10) Under capability choose ```Web player```<br>
<img width="604" alt="direct user" src="https://github.com/Gurudutt-Goswami/Spotfire-Admin/assets/86184439/3ed25344-9ba5-463c-9f4d-3db22f79f2d5"><br>
11) Click on install and start. You can follow the same process for automation services.
   



### Spotfire Platform Edition Setup
1) Server installation<br>
   a) Download product at edelivery.tibco.com<br>
   b) Install database & server<br>
      i) Go to scripts folder > mssql_install > create_database.bat > Edit<Br>
      ii) Set following parameters <Br>
      <img width="227" alt="parameters from database bat file" src="https://github.com/Gurudutt-Goswami/Spotfire-Admin/assets/86184439/e9020917-9c32-4e2b-8b48-87e9d721c941"><Br>
      iii) Save this file & run this as admin<Br>
      iv) Now open mssql & confirm whether the database is created or not<br>
      v) Install server <Br>
         a) Set NTLM Auth : Do not download option<br>
         b) Make sure to check path & correct port numbers<br>   
   c) Configuration<br>
   Open configuration tool to setup bootstrap<br>
      <img width="476" alt="configuration" src="https://github.com/Gurudutt-Goswami/Spotfire-Admin/assets/86184439/4a4971b7-3aeb-4028-a74d-89c648cf6aaa"><br>
   Once the bootstrap configuration is done save the configuration in the database<br>
   Go to services to start server & then start configure tibco spotfire server & as soon as you provide the password for the configuration tool you are done <br>
   Now in administrator tab in configuration tool, add the user & promote it to admin<br>
   Restart the server & login with your admin credential, ideally you should able to see all services.<br>
   <img width="556" alt="services" src="https://github.com/Gurudutt-Goswami/Spotfire-Admin/assets/86184439/f6e84a77-206f-4b38-89c0-a1071850cac4">

3) Server deployment<br>
   a) pre-requisite is to install spotfire server<Br>
   b) Login into Spotfire server to deploy packages ,add ones etc.<br>
   c) Go to ```Deployment and packages``` > click on add packages & browse ```(generally the .sdn file)```<br>
   d) After upload ```Validate area``` and then click on ```Save area```.<br>
   Note: This deployment area can be different for different groups.
5) Analyst installation
6) Node manager installation


### LTS and Mainstream
starting from Spotfire version 7.11, there are two types of Spotfire releases - mainstream and LTS (Long Term Support). Mainstream versions are released approximately every 1-2 months - LTS releases approximately every 12-18 months.<br>
```https://docs.tibco.com/pub/spotfire/general/LTS/spotfire_LTS_releases.htm```
