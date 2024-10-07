# openshiftcustomdashboard
Project for customizing the OCP Dashboard.

1: TO get the logo changed on the OCP login screen run the command from local machine which has access to the Openshift.
#Note 
The custom image height must be 60 pixel. If you have a exiting image and would like to conver the image then you can use GIMP, open the image -> go to Image -> Select resize then put the height as 60 px and save it.

oc create configmap console-custom-logo --from-file sunbeam60px.jpg -n openshift-config

2: run the command 
oc edit consoles.operator.openshift.io cluster

and add following line.
```
spec:
  customization:
    customLogoFile:
      key: sunbeam60px.jpg
      name: console-custom-logo
    customProductName: Yajuvendra's Console
```

