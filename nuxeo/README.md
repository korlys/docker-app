```
docker run 
    --name mynuxeo 
    --rm -ti -p 8080:8080 
    -e NUXEO_PACKAGES="nuxeo-web-ui nuxeo-dam nuxeo-drive nuxeo-showcase-content nuxeo-template-rendering nuxeo-template-rendering-samples nuxeo-spreadsheet" 
    nuxeo
```