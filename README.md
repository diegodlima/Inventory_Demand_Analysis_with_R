# Grupo Bimbo Inventory Demand
This project is part of the Data Science Formation taugh by Data Science Academy: https://www.datascienceacademy.com.br/
<br />
This original project is posted on https://www.kaggle.com/c/grupo-bimbo-inventory-demand
<br />
<h3>Files Description</h3>
- <b>.csv files:</b> contain the datasets (described below)<br />
- <b>Demand.R:</b> contain the script of the project<br />
- <b>Demand.Rmd:</b> contain the markdown script<br />
- <b>Demand.html:</b> <u>this file is the compiled report</u>
<hr />
<h2>Description</h2>
Planning a celebration is a balancing act of preparing just enough food to go around without being stuck eating the same leftovers for the next week. The key is anticipating how many guests will come. Grupo Bimbo must weigh similar considerations as it strives to meet daily consumer demand for fresh bakery products on the shelves of over 1 million stores along its 45,000 routes across Mexico.
<br /><br />
Currently, daily inventory calculations are performed by direct delivery sales employees who must single-handedly predict the forces of supply, demand, and hunger based on their personal experiences with each store. With some breads carrying a one week shelf life, the acceptable margin for error is small.
<br /><br />
In this competition, Grupo Bimbo invites Kagglers to develop a model to accurately forecast inventory demand based on historical sales data. Doing so will make sure consumers of its over 100 bakery products aren’t staring at empty shelves, while also reducing the amount spent on refunds to store owners with surplus product unfit for sale.
<h2>Data description</h2>
In this competition, you will forecast the demand of a product for a given week, at a particular store. The dataset you are given consists of 9 weeks of sales transactions in Mexico. Every week, there are delivery trucks that deliver products to the vendors. Each transaction consists of sales and returns. Returns are the products that are unsold and expired. The demand for a product in a certain week is defined as the sales this week subtracted by the return next week.
<br /><br />
The train and test dataset are split based on time, as well as the public and private leaderboard dataset split.
<br /><br />
<u>Things to note:</u>
<br />
There may be products in the test set that don't exist in the train set. This is the expected behavior of inventory data, since there are new products being sold all the time. Your model should be able to accommodate this.
There are duplicate Cliente_ID's in cliente_tabla, which means one Cliente_ID may have multiple NombreCliente that are very similar. This is due to the NombreCliente being noisy and not standardized in the raw data, so it is up to you to decide how to clean up and use this information. 
<br /><br />
The adjusted demand (Demanda_uni_equil) is always >= 0 since demand should be either 0 or a positive value. The reason that Venta_uni_hoy - Dev_uni_proxima sometimes has negative values is that the returns records sometimes carry over a few weeks.
<br />
<h3>File descriptions</h3>
<b>train_set2.csv —</b> a sample of 500,000 of the original training set<br />
<b>cliente_tabla.csv —</b> client names (can be joined with train/test on Cliente_ID)<br />
<b>producto_tabla.csv —</b> product names (can be joined with train/test on Producto_ID)<br />
<b>town_state.csv —</b> town and state (can be joined with train/test on Agencia_ID)<br />
<br />
<h3>Data fields</h3>
<b>Semana —</b> Week number (From Thursday to Wednesday)<br />
<b>Agencia_ID —</b> Sales Depot ID<br />
<b>Canal_ID —</b> Sales Channel ID<br />
<b>Ruta_SAK —</b> Route ID (Several routes = Sales Depot)<br />
<b>Cliente_ID —</b> Client ID<br />
<b>NombreCliente —</b> Client name<br />
<b>Producto_ID —</b> Product ID<br />
<b>NombreProducto —</b> Product Name<br />
<b>Venta_uni_hoy —</b> Sales unit this week (integer)<br />
<b>Venta_hoy —</b> Sales this week (unit: pesos)<br />
<b>Dev_uni_proxima —</b> Returns unit next week (integer)<br />
<b>Dev_proxima —</b> Returns next week (unit: pesos)<br />
<b>Demanda_uni_equil —</b> Adjusted Demand (integer) (This is the target you will predict)<br />
