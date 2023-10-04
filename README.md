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
Spotfire server front end port : 80
Backend registration port : 9080 
Backend communication port : 9443 
<img width="512" alt="Screenshot 2023-10-04 183630" src="https://github.com/Gurudutt-Goswami/Spotfire-Admin/assets/86184439/678041cb-4546-4efa-bd97-5d2b1c01ba20">

Note : Open configuration tool for fresh installation.



### LTS and Mainstream
starting from Spotfire version 7.11, there are two types of Spotfire releases - mainstream and LTS (Long Term Support). Mainstream versions are released approximately every 1-2 months - LTS releases approximately every 12-18 months.
