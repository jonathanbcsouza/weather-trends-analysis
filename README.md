# Project 1 - Explore weather trends

![](https://paper-attachments.dropbox.com/s_52387B7D228925F713EEEF9A9749DED8659CE2C30C206BAB49C2A7F83DCE156E_1588376646030_image.png)


**Summary**
This project is a comparison of the global temperature over the years with the data of de capital of New Zealand, Wellington.

**Key considerations:**
Show clear data, the data has to be accurate as much as possible, has to be easy to read and show relevant information that can help to shape action plans.

**1-Extracting**

I downloaded all Udacity's database available by executing the followings commands in the SQL workspace.


    SELECT * FROM global_data
    SELECT * FROM city_list
    SELECT * FROM city_data

In addition, in the SQL workspace, I ran the following code to visualise all available data in the New Zealand capital and I saved this into a new spreadsheet called “**city_data_where_nz":**


    SELECT * FROM city_data WHERE country='New Zealand'


![Udacity's SQL Workspace](https://paper-attachments.dropbox.com/s_52387B7D228925F713EEEF9A9749DED8659CE2C30C206BAB49C2A7F83DCE156E_1588499596021_image.png)


The only city found in their database in New Zealand was Wellington.

**2-Merging information**

Then I opened the spreadsheet **global_data** and then created **city_data_where_nz** with Excel.

In the spreadsheet **global_data,** I created a new column called "Wellington, NZ" and I used the VLOOKUP in order to get all values from the another spreadsheet:

    =IFERROR(VLOOKUP(A105,city_data_where_nz.csv!$A:$D,4,FALSE),"Not Available")
![Filtering only available data](https://paper-attachments.dropbox.com/s_52387B7D228925F713EEEF9A9749DED8659CE2C30C206BAB49C2A7F83DCE156E_1588378217791_image.png)



The ifError formula was needed because for some years the database had no data for Wellington, therefore, I decided to leave the cells as "not available", which means that the data could not be found in the **city_data_where_nz** spreadsheet .
Then I applied a filter in order to keep only the years where I could find data in both compared spreadsheets.



**3- Calculations**

I used this way to find out what was the percentage difference between every year.

![Yearly increase rate global](https://paper-attachments.dropbox.com/s_52387B7D228925F713EEEF9A9749DED8659CE2C30C206BAB49C2A7F83DCE156E_1588492790836_image.png)
![Yearly increase rate local](https://paper-attachments.dropbox.com/s_52387B7D228925F713EEEF9A9749DED8659CE2C30C206BAB49C2A7F83DCE156E_1588492910339_image.png)


And the following formulas to create this table:

![Data summary, formulas taken.](https://paper-attachments.dropbox.com/s_52387B7D228925F713EEEF9A9749DED8659CE2C30C206BAB49C2A7F83DCE156E_1588504429260_image.png)


The moving average used to smooth the data was taken by 10 years time.

![10 years - moving average](https://paper-attachments.dropbox.com/s_52387B7D228925F713EEEF9A9749DED8659CE2C30C206BAB49C2A7F83DCE156E_1588505249925_image.png)


**4- Charts**

![Wellington X Global comparison](https://uc3e808e50705674164e134d20a5.previews.dropboxusercontent.com/p/thumb/ABB976esbaCiF4w-yCxOZFmS7dYPsYGuXabFO8dPd8a_M3J5s4AxduWqRkK567xSal2uJLta9XIIh6oj0vEx7yI9OfbRNsBEcpDj5-cWeOL-kUBR58AC8nuCdrXe998RR4E_bGRpov29kqkoL1ej0pWP-YMcktGQZAMqB2WWUT7yeiV_nFwDATlJPYT9lmex9bLEO7dO9zzI7TWoF5JFxtqtFIG-o1QCOjs7NI4yNbjMUfAN2zhCxM0CNBRcwYL1P5is_S0cUkkaYpwTmzlaknY7twZUWesschvQGvPAjMRt0L8s7jCZRCov-MmHrWT4I3_xL70gciKrzZiH_KDYiVuTTP_nj4Z384U6llqcJe_ejTZRagmGS052o7VPqNqurc3tA2Cm9nX1jRGp3JsL_ZTI/p.png)



![Global and local predictions.](https://uc8315ff5407db6c77d93933e782.previews.dropboxusercontent.com/p/thumb/ABDXRgzt3VAYtmOm1aqHmHiKTt7ippt6U65blqd8DeRLBx7Q2Vn5c8Lj4PUiDeVabDhTKrUIDEaTJrsZwVYeyqEElTeyMXF6zyGn7VwhYVUNJAXtuEyG6Cu53m4xdBanu1kuc2-bromrTOuEVoH6OE47nT67W6eh6ctBMEFrde8sBExrMrHk8KuDNEg53cH0vnaM3dGFTD2kktPJ6w4OwELWyAtZmH8DBzlPCkbuS2vj-OlcbS84KauVL42xxl53gB4_PyTbAaRg9d7ZQbNIV_ZXV716J1oFLv5KWW1fVZXSaYqXvmpp0jxykaGcEhTH7NwSBl0nTm8d5I8SNX9KMDmetXQL9ChTmUIVnNccVPdD2TBM8oa4sJxnLBgtEDbQzZr33Dr6IzlDu_uz0tKm9ew5/p.png)



![Min, Max Temperatures and difference over the years.](https://ucb124cd6043242454f92141d02f.previews.dropboxusercontent.com/p/thumb/ABACP6oUbG9VK5X8-KXqiw9cSKv7OFDEnxX5U0GL2M3d1Xsv_h-RRqtFS2mNcuv1maSxXRCwVDWlM4YkjtWGPbJFAf0ZrAzWJ6zcsvqFdkT9MSWy4tl0LTQ9x3dR5dP83AcGX2-yKvZHy9kDjRm_G8F87q8kX2202q2v9cvHORqFBGDzLu5RgkR9EX0Ed6HZzEs31kpMfWVD2jlHi3xNAz1CCubDK5u-P8qHpp5WXt74FDWDNBegOB8MCNCwg_t968w451M3kLOGgFUrvhgkZrjtAWi8QmF4afI12Wl0OAzqpFWYbeKjeUqvilBHLfv6oU83Ixa3Oi2tnANFP3vUj_rX2btzGj3iIJ1lS5Forv2-GaPD9wyvUGhDO-8JqGMfTKM/p.png)


**5- Predictions**

This is a rough predictions of what would be the next years temperature globally and locally.

I have got the global and local average temperature and I used its rate as a constant to find what would be the next year temperature.


    Logic: (Previous year temperature X Mean temperature increase rate)+ Previous year temperature
    Formula:(B12*global_data!$K$115)+B12 


![](https://paper-attachments.dropbox.com/s_52387B7D228925F713EEEF9A9749DED8659CE2C30C206BAB49C2A7F83DCE156E_1588505089305_image.png)


**Final considerations:**


- Both average temperatures have been increasing over time.
- Both have a higher average temperature now comparing with the past.
- Over 130 years, the Wellington temperature has increased 1.45 C° and the global temperature 4.05 C°
- The Wellington temperature has not been increasing as the global is.
- The global temperature increase rate is higher than in Wellington, which means the world itself has a more climate impact than Wellington.
- The global data has a lower standard error, which means fewer fluctuations, more data reliability.
- The global average temperature has been approaching the Wellington temperature over the years.
- The global temperature would match with the Wellington around the year 2696.
- The Wellington city in New Zealand apparently do more effective environmental protective actions than other countries.

**References:**

Accessed at 03/05/2020:
https://www.usatoday.com/story/money/2019/07/14/climate-change-countries-doing-most-least-to-protect-environment/39534413/

