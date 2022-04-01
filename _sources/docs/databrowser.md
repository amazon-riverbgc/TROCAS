# TROCAS Data Browser

The TROCAS Data Browser provides convenient overviews and exploration of TROCAS data. Currently it aggregates sensor data from the TROCAS project across all TROCAS transects conducted so far and collected from a boat in continuous "underway" mode while transiting or remaining stationary at a location.

```{link-button} https://trocasdata-1.herokuapp.com
:text: Go to TROCAS Data Browser
:tooltip: https://trocasdata-1.herokuapp.com
:classes: btn-light btn-lg
```

It may take 10 seconds or more for the application to start up. If you encounter an "Appplication error" page, please hit the browser reload button (typically `Ctrl-r`) to try again. For help using the Data Browser, see its "About Data Browser" tab. The main component of the application is in the "Data Browser" tab. The "Inventory" tab presents an inventory table for each TROCAS transect and a list of currently known data gaps or issues that need to be addressed.

## Data

Sensor types currently processed and included in the Data Browser are [EXO Sonde](https://www.ysi.com/exo), [Licor CO2](https://www.licor.com/env/products/gas_analysis/), [Picarro](https://www.picarro.com/products/g2201i_isotopic_analyzer) and GPS. The data browser does not yet include data from ADCP sensors, experiments (such as respiration incubations) or laboratory analyses of samples. Data presented are based on raw sensor output files processed and averaged into 1-minute bins. Binned data from each sensor are then joined on matching time-interval bins. Sensor data that don't have a corresponding GPS 1-minute bin are not presented on this application; such data will require further investigation to attach geospatial coordinates.

## Technology

The TROCAS Data Browser is an online "dashboard" application (app) developed in Python using the [HoloViz](https://holoviz.org/) visualization software ecosystem, particularly the [Panel](https://panel.holoviz.org/) dashboarding library. The dashboard code is maintained in a Jupyter notebook ([trocas_pannelapp_1.ipynb](https://github.com/amazon-riverbgc/trocas-herokuapp1/blob/master/trocas_pannelapp_1.ipynb)) and associated Python modules. All the code is openly available on the GitHub repository for the Data Browser: [https://github.com/amazon-riverbgc/trocas-herokuapp1](https://github.com/amazon-riverbgc/trocas-herokuapp1)

The app is deployed online through the [Heroku](https://www.heroku.com) cloud platform. However, it can also be run locally in your own computer or computational resource; please see the information found in the GitHub repository and in the Jupyter notebook, and post questions there as [GitHub issues](https://github.com/amazon-riverbgc/trocas-herokuapp1/issues).
