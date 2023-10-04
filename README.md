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
3) Backend communication port : 9443 
<img width="512" alt="Screenshot 2023-10-04 183630" src="https://github.com/Gurudutt-Goswami/Spotfire-Admin/assets/86184439/678041cb-4546-4efa-bd97-5d2b1c01ba20">

Note : Open configuration tool for fresh installation.
Upgrade tool can also be located under Spotfire server installation directory > Tools > Upgrade Folder 

File Location
<img width="526" alt="file location" src="https://github.com/Gurudutt-Goswami/Spotfire-Admin/assets/86184439/b42aeaa0-f2d9-4af2-96ae-563b89c9d9b3">
<img width="179" alt="database things" src="https://github.com/Gurudutt-Goswami/Spotfire-Admin/assets/86184439/7aa30dbb-592c-4c40-8900-a7fac09b9c03">
<img width="533" alt="database things 2" src="https://github.com/Gurudutt-Goswami/Spotfire-Admin/assets/86184439/05a320fd-ade0-4702-b37d-35ea6b8cad71">

If you select to take detail from previous database then it will take information from bootstrap file.

The upgrade process generally takes around 5 min , once it completes we should check whether we it has found any issues while upgrading. We can find this information right after the upgrade in the wizard only or in ```upgrade-issues.html``` file under ```warning/issues``` path.

Once the upgrade is done the next step is to deploy the client package 
1) Login to admin UI
2) Go to deployments & packages
3) Click on Add packges & browse client deployment kit & upload.
4) Click on Validate area to check any compatibility issue with the package.
5) Click on Save area.
Once its deployed try starting Spotfire client & change server port if required. Once it open up it will throw a pop to install/upgrade to your installed version.


### LTS and Mainstream
starting from Spotfire version 7.11, there are two types of Spotfire releases - mainstream and LTS (Long Term Support). Mainstream versions are released approximately every 1-2 months - LTS releases approximately every 12-18 months.
