# Auto Translation and Reverse Geocoding
This notebook walks through auto-translation and reverse-geocoding processes.

### Example:

#### Input:

<img width="640" alt="Screen Shot 2021-10-27 at 1 32 49 PM" src="https://user-images.githubusercontent.com/44503223/139125844-1df14eed-c4a6-434d-acee-ee7ed998ae01.png">

#### Output: 

<img width="641" alt="Screen Shot 2021-10-27 at 1 34 00 PM" src="https://user-images.githubusercontent.com/44503223/139125993-8c2fe34a-b5eb-482b-b44b-190a1a938440.png">

### Use lat/lng to find zip code

<img width="277" alt="Screen Shot 2021-10-27 at 1 41 05 PM" src="https://user-images.githubusercontent.com/44503223/139127036-efb04f4f-b7d9-4f63-b654-05ef15acfae7.png">

```python
zipcodes=[]
addresses=[]
input_list=[]
for i in sample['lat_lng']:
    time.sleep(1)
    try:
        location = geolocator.reverse(str(i[0])+","+str(i[1]))
        zipcodes.append(location.raw['address']['postcode'])
        addresses.append(location.address)
        input_list.append(i)
    except:
        input_list.append(i)
        zipcodes.append('error')
        addresses.append('error')
```

### Reference:
- googletrans https://pypi.org/project/googletrans/
- GeoPy’s documentation https://geopy.readthedocs.io/en/stable/

## Learn More

For more information, please check out the [Project Portfolio](https://tingting0618.github.io).
