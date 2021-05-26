Blue/Green deployment
 - Blue - Currently live
 - Green - newer version to deploy

1. deploy blue app
   cf push pal-tracker -n pal-tracker-sneela
2. deploy green app
   cf push pal-tracker2 -n pal-tracker-sneela-temp
3. Map original route to Green
   cf map-route pal-tracker2 apps.evans.pal.pivotal.io -n pal-tracker-sneela
4. Unmap route to Blue
   cf unmap-route pal-tracker apps.evans.pal.pivotal.io -n pal-tracker-sneela
5. Remove temp route to Green
   cf unmap-route pal-tracker2 apps.evans.pal.pivotal.io -n pal-tracker-sneela-temp
6. 