# EWARS plus Dashboard R scripts for deployment in shinyapps.io/ shiny server

NB: Please download R-inla zipped package file 'INLA_21.02.23.tar.gz'.This file can be found in the link :https://inla.r-inla-download.org/R/stable/src/contrib/INLA_21.02.23.tar.gz Place the 'INLA_21.02.23.tar.gz' file in the same folder as the shiny App

To publish the dashboard on shinyapps.io you can run the command below in R:
## Note: This assumes you already have an account in shinyapps.io and configured with rsconnect. If not, create account.
library(rsconnect)

## app.dir <-"Directory where you saved the downloaded the dashboard scripts"
## appName<-'dashboard name'

  deployApp(
    appDir = app.dir,
    appName = appName,
    forceUpdate = T,
    launch.browser=F
  )
 
## You can increase the default memory size in shinyapps by running the configuration:

configureApp(
    appDir = app.dir,
    redeploy = TRUE,
    appName = appName,
    size = "xxxlarge",
    #instances=1,
    logLevel="quiet"
  )

To setup Shiny server  (linux) follow the guidelines on:https://docs.rstudio.com/shiny-server/

You can test dashboard I using the demo data and shapefiles included in this repository under the folder Demo_data

After running dashboard I, you can test dashboard II using the 'Demo.Data.Prospective.csv' file also under the Demo_data folder
