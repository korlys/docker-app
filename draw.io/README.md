docker run -it  
--rm 
--name="draw" 
--mount type=bind,source="$(pwd)"/PreConfig.js,target=/usr/local/tomcat/webapps/draw/js/PreConfig.js 
--mount type=bind,source="$(pwd)"/PostConfig.js,target=/usr/local/tomcat/webapps/draw/js/PostConfig.js 
-p 8080:8080 
-p 8443:8443 
fjudith/draw.io
