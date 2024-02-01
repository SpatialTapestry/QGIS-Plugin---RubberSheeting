QGIS seems to be missing 'Spatial Upgrade' tools to things like Rubber Sheeting or Two Point Transformations.
Spatial Tapestry has been doing 'Spatial Upgrades' for Utilities and Local Government for 30 years, and has an excellent Windows Desktop Application which is far more advanced than this Plugin. The effort to port that functionality to QGIS would be maybe 3 to 5 years. Please feel free to email the author for the User Manual.
However for many the Rubber Sheeting algorithm provided will adequate. This is nothing more than calculating the weighted average shift from the 10 nearest Shift Vectors.
Spatial Tapestry would love to hear back from anyone with ideas for other algorithms, happy to look at coding them if they sound interesting.


It is assumed the user knows: 
1/ how to make one or more themes 'Active' in the QGIS Menu 
2/ the correct database connection parameters for their database 
3/ the SRID/EPSG that the themes will be stored in 
4/ the database connectors have been installed.
Installation Instructions:
QGIS 3.28 is recommended. 
Do not install Python, instead we will use the Python installed with QGIS. (Installing Python 3.12 on Windows causes problems)
All 3 database connectors must be installed otherwise to code will return errors. Alternatively the Python Source code can be modified to remove references to any unwanted connectors.
Ubuntu pip3 install -U psycopg2 pip3 install -U oracledb pip3 install -U pyodbc
Windows 10/11 On Windows the "PythonPath" Environment Variable must be set - be sure to adjust this to your particular computer and QGIS Version: PYTHONPATH C:\Program Files\QGIS 3.28.15\apps\qgis\python;C:\Program Files\QGIS 3.28.15\apps\qgis\python\plugins;C:\Program Files\QGIS 3.28.15\apps\Qt5\plugins;C:\Program Files\QGIS 3.28.15\share\gdal;
C:\Program Files\QGIS 3.28.15\apps\Python39\Scripts\pip3 install -U psycopg2 C:\Program Files\QGIS 3.28.15\apps\Python39\Scripts\pip3 install -U oracledb C:\Program Files\QGIS 3.28.15\apps\Python39\Scripts\ pip3 install -U pyodbc
Devart components
The Devart components are used by the 'pyodbc' connector to deal with the MS SQL Server and Oracle. i.e. If you are uploading to PostgreSQL or Oracle (and the oracledb connector is working) then the Devart components are not necessary. Note: QGIS 3.28.15 has Python 3.9 as part of its installation!
The following URLs will help with the DEVART components.
https://www.devart.com/python/oracle/download.html
Python Connector for Oracle 1.0 - Python 3.9 for Windows
Or
Python Connector for Oracle 1.0 - Python 3.9 for Linux
cd C:\Users\r\Downloads\devart_oracle_cp39_win\DevartPythonOracle\whl
"C:\Program Files\QGIS 3.28.15\apps\Python39\Scripts\pip3" install devart_oracle_connector-1.0.1-cp39-cp39-win_amd64.whl
https://www.devart.com/python/sqlserver/download.html
Python Connector for SQL Server 1.0 - Python 3.9 for Windows
Or
Python Connector for SQL Server 1.0 - Python 3.9 for Linux
cd C:\Users\r\Downloads\devart_sqlserver_cp39_win\DevartPythonSqlServer\whl
"C:\Program Files\QGIS 3.28.15\apps\Python39\Scripts\pip3" install devart_sqlserver_connector-1.0.1-cp39-cp39-win_amd64.whl
