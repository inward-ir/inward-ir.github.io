Deployment
==========

--------------------------------------------------------------------------------

## Application

1. Build Application with '-tags release' argument
2. Copy binary file to destination
3. Copy 'resource' directory to destination
4. Edit and config 'resource/conf.production.yml' file
5. Set environment variable 'ENVIRONMENT' to 'PRODUCTION'

## Web

1. Build Web with '-tags release' argument
2. Copy binary file to destination
3. Copy 'resource' directory to destination
4. Copy 'views' directory to destination
