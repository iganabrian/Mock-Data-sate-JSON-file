# Importing python request 
Import requests mporting pandas 

```python

### import pandas library
import pandas as pd

### input the url link from github
url = "https://raw.githubusercontent.com/iganabrian/Mock-Data-sate-JSON-file/refs/heads/main/mock.json"

response = requests.get(url)

### writing a code to check if the request worked
if response.status_code == 200:
    print('Successfully imported the mock data')
else:
    print('Mock data not found')

### Turn the imported data in a DataFrame
data = response.json()
df = pd.DataFrame(data)

### Display top 5
df.head(5)
df.to_csv('Mock Data.csv', index=False)

```

### Part 3: Working with DummyJSON API Endpoints

Using the Python requests library, extract data from the following DummyJSON endpoints:


Products endpoint
https://dummyjson.com/productsI 


Carts endpoint
https://dummyjson.com/carts

```python

url_products = 'https://dummyjson.com/products'

response = requests.get(url_products)

if response.status_code == 200:
    print ('Product data retrived')
else:
    print('Product data not found')

```

### Turn data into a DataFrame

```python

products = response.json()

products_df = pd.DataFrame(products)

products_df.head()

### Export as CSV
products_df.to_csv('Products Dummy Data.csv', index=False)

#### Carts endpoint
url_carts = 'https://dummyjson.com/carts'

response = requests.get(url_products)

if response.status_code == 200:
    print ('Carts data retrived')
else:
    print('Carts data not found')
### Turn Carts JSON File to DataFrame
carts = response.json()

carts_df = pd.DataFrame(carts)

carts_df.head()

### Carts DataFrame To csv
products_df.to_csv('Carts Dummy Data.csv', index=False)

```