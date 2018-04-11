
# Lists and Maps Lab

### Introduction

Ok, so now that we have a sense of how to read from a list and alter a list in Python, let's see how our knowledge of lists can help us in creating data visualizations by plotting maps. 

### Working with lists and maps

As we know, lists are used to store a collection of data.  In describing a city, we can use lists to organize our data in all sorts of ways.  For example, here is a list of neighborhoods in the city of Buenos Aires.


```python
neighborhoods = ['Palermo', 'Ricoleta', 'Santelmo', 'Puerto Madero', 'Belgrano', 'La Boca']
```

> Press shift + enter on this cell and all following code cells.

Select the first element of the list, and assign it to the variable `palermo`.


```python
palermo = None
```

Select the last element of the list, and assign it to the variable la_boca.


```python
la_boca = None
```

Beyond the neighborhoods, another thing that we can think of representing as a collection are the coordinates of a city, latitude and longitude.  The first attribute is latitude and the second is longitude.


```python
coordinates = [-34.6037, -58.3816]
```

Set the latitude of Buenos Aires equal to `ba_latitude` and set the longitude to be Buenos Aires to be `ba_longitude`.


```python
ba_latitude = None 
```


```python
ba_longitude = None
```

Now let's see if we can display this as a map.

First we download a mapping library with `pip`. Remember a library is simply a tool comprised of code hosted somewhere else on the internet and which we download to use in our current project. Pip is another tool that allows us to easily download various Python libraries from the Internet.  


```python
!pip install folium
```

Press shift + enter on the above code, and our `folium` library is available to us.  Now we just tell Python that we will be using `folium` in our codebase by writing `import folium` in the next cell. Once the import is complete we will be able to display some maps with the help of `folium`.


```python
import folium
buenos_map = folium.Map([-34.6037, -58.3816])
buenos_map
```

All of that from a couple of lines of code.  Let's understand it:

```python
import folium
buenos_map = folium.Map([-34.6037, -58.3816])
buenos_map
```

> [Folium](https://github.com/python-visualization/folium) is a mapping library built on Python.  We created a representation of a map, by referencing the `folium.Map` function and passing through a list.  That list represents the latitude and longitude, just like we saw previously.  The map object is stored as the variable `buenos`.  Since `buenos` is the last line of a cell, the map is displayed.

Now we can also add a marker to this map.


```python
buenos_marker = folium.Marker([-34.6037, -58.3816])
buenos_marker.add_to(buenos_map)
```




    <folium.map.Marker at 0x1137d1d68>



So we used the `folium` library to create a marker.  We specified the coordinates of the marker as a list. Finally, we added the marker to our map with the `add_to` function.

Let's see our updated map!  We see our map simply by referencing our `buenos_map` variable.


```python
buenos_map
```




<div style="width:100%;"><div style="position:relative;width:100%;height:0;padding-bottom:60%;"><iframe src="data:text/html;charset=utf-8;base64,PCFET0NUWVBFIGh0bWw+CjxoZWFkPiAgICAKICAgIDxtZXRhIGh0dHAtZXF1aXY9ImNvbnRlbnQtdHlwZSIgY29udGVudD0idGV4dC9odG1sOyBjaGFyc2V0PVVURi04IiAvPgogICAgPHNjcmlwdD5MX1BSRUZFUl9DQU5WQVMgPSBmYWxzZTsgTF9OT19UT1VDSCA9IGZhbHNlOyBMX0RJU0FCTEVfM0QgPSBmYWxzZTs8L3NjcmlwdD4KICAgIDxzY3JpcHQgc3JjPSJodHRwczovL2Nkbi5qc2RlbGl2ci5uZXQvbnBtL2xlYWZsZXRAMS4yLjAvZGlzdC9sZWFmbGV0LmpzIj48L3NjcmlwdD4KICAgIDxzY3JpcHQgc3JjPSJodHRwczovL2FqYXguZ29vZ2xlYXBpcy5jb20vYWpheC9saWJzL2pxdWVyeS8xLjExLjEvanF1ZXJ5Lm1pbi5qcyI+PC9zY3JpcHQ+CiAgICA8c2NyaXB0IHNyYz0iaHR0cHM6Ly9tYXhjZG4uYm9vdHN0cmFwY2RuLmNvbS9ib290c3RyYXAvMy4yLjAvanMvYm9vdHN0cmFwLm1pbi5qcyI+PC9zY3JpcHQ+CiAgICA8c2NyaXB0IHNyYz0iaHR0cHM6Ly9jZG5qcy5jbG91ZGZsYXJlLmNvbS9hamF4L2xpYnMvTGVhZmxldC5hd2Vzb21lLW1hcmtlcnMvMi4wLjIvbGVhZmxldC5hd2Vzb21lLW1hcmtlcnMuanMiPjwvc2NyaXB0PgogICAgPGxpbmsgcmVsPSJzdHlsZXNoZWV0IiBocmVmPSJodHRwczovL2Nkbi5qc2RlbGl2ci5uZXQvbnBtL2xlYWZsZXRAMS4yLjAvZGlzdC9sZWFmbGV0LmNzcyIgLz4KICAgIDxsaW5rIHJlbD0ic3R5bGVzaGVldCIgaHJlZj0iaHR0cHM6Ly9tYXhjZG4uYm9vdHN0cmFwY2RuLmNvbS9ib290c3RyYXAvMy4yLjAvY3NzL2Jvb3RzdHJhcC5taW4uY3NzIiAvPgogICAgPGxpbmsgcmVsPSJzdHlsZXNoZWV0IiBocmVmPSJodHRwczovL21heGNkbi5ib290c3RyYXBjZG4uY29tL2Jvb3RzdHJhcC8zLjIuMC9jc3MvYm9vdHN0cmFwLXRoZW1lLm1pbi5jc3MiIC8+CiAgICA8bGluayByZWw9InN0eWxlc2hlZXQiIGhyZWY9Imh0dHBzOi8vbWF4Y2RuLmJvb3RzdHJhcGNkbi5jb20vZm9udC1hd2Vzb21lLzQuNi4zL2Nzcy9mb250LWF3ZXNvbWUubWluLmNzcyIgLz4KICAgIDxsaW5rIHJlbD0ic3R5bGVzaGVldCIgaHJlZj0iaHR0cHM6Ly9jZG5qcy5jbG91ZGZsYXJlLmNvbS9hamF4L2xpYnMvTGVhZmxldC5hd2Vzb21lLW1hcmtlcnMvMi4wLjIvbGVhZmxldC5hd2Vzb21lLW1hcmtlcnMuY3NzIiAvPgogICAgPGxpbmsgcmVsPSJzdHlsZXNoZWV0IiBocmVmPSJodHRwczovL3Jhd2dpdC5jb20vcHl0aG9uLXZpc3VhbGl6YXRpb24vZm9saXVtL21hc3Rlci9mb2xpdW0vdGVtcGxhdGVzL2xlYWZsZXQuYXdlc29tZS5yb3RhdGUuY3NzIiAvPgogICAgPHN0eWxlPmh0bWwsIGJvZHkge3dpZHRoOiAxMDAlO2hlaWdodDogMTAwJTttYXJnaW46IDA7cGFkZGluZzogMDt9PC9zdHlsZT4KICAgIDxzdHlsZT4jbWFwIHtwb3NpdGlvbjphYnNvbHV0ZTt0b3A6MDtib3R0b206MDtyaWdodDowO2xlZnQ6MDt9PC9zdHlsZT4KICAgIAogICAgICAgICAgICA8c3R5bGU+ICNtYXBfY2U2MjdkYTU4MmFjNDg3ZjljZTdmOGQyZDZlMTE1NTAgewogICAgICAgICAgICAgICAgcG9zaXRpb24gOiByZWxhdGl2ZTsKICAgICAgICAgICAgICAgIHdpZHRoIDogMTAwLjAlOwogICAgICAgICAgICAgICAgaGVpZ2h0OiAxMDAuMCU7CiAgICAgICAgICAgICAgICBsZWZ0OiAwLjAlOwogICAgICAgICAgICAgICAgdG9wOiAwLjAlOwogICAgICAgICAgICAgICAgfQogICAgICAgICAgICA8L3N0eWxlPgogICAgICAgIAo8L2hlYWQ+Cjxib2R5PiAgICAKICAgIAogICAgICAgICAgICA8ZGl2IGNsYXNzPSJmb2xpdW0tbWFwIiBpZD0ibWFwX2NlNjI3ZGE1ODJhYzQ4N2Y5Y2U3ZjhkMmQ2ZTExNTUwIiA+PC9kaXY+CiAgICAgICAgCjwvYm9keT4KPHNjcmlwdD4gICAgCiAgICAKCiAgICAgICAgICAgIAogICAgICAgICAgICAgICAgdmFyIGJvdW5kcyA9IG51bGw7CiAgICAgICAgICAgIAoKICAgICAgICAgICAgdmFyIG1hcF9jZTYyN2RhNTgyYWM0ODdmOWNlN2Y4ZDJkNmUxMTU1MCA9IEwubWFwKAogICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgJ21hcF9jZTYyN2RhNTgyYWM0ODdmOWNlN2Y4ZDJkNmUxMTU1MCcsCiAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICB7Y2VudGVyOiBbLTM0LjYwMzcsLTU4LjM4MTZdLAogICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgem9vbTogMTAsCiAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICBtYXhCb3VuZHM6IGJvdW5kcywKICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgIGxheWVyczogW10sCiAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICB3b3JsZENvcHlKdW1wOiBmYWxzZSwKICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgIGNyczogTC5DUlMuRVBTRzM4NTcKICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgfSk7CiAgICAgICAgICAgIAogICAgICAgIAogICAgCiAgICAgICAgICAgIHZhciB0aWxlX2xheWVyXzdlN2YyY2Y1YTAzNzQ0NTg4NzQ3NDZmNDM3ZmM4ZjcxID0gTC50aWxlTGF5ZXIoCiAgICAgICAgICAgICAgICAnaHR0cHM6Ly97c30udGlsZS5vcGVuc3RyZWV0bWFwLm9yZy97en0ve3h9L3t5fS5wbmcnLAogICAgICAgICAgICAgICAgewogICJhdHRyaWJ1dGlvbiI6IG51bGwsCiAgImRldGVjdFJldGluYSI6IGZhbHNlLAogICJtYXhab29tIjogMTgsCiAgIm1pblpvb20iOiAxLAogICJub1dyYXAiOiBmYWxzZSwKICAic3ViZG9tYWlucyI6ICJhYmMiCn0KICAgICAgICAgICAgICAgICkuYWRkVG8obWFwX2NlNjI3ZGE1ODJhYzQ4N2Y5Y2U3ZjhkMmQ2ZTExNTUwKTsKICAgICAgICAKICAgIAoKICAgICAgICAgICAgdmFyIG1hcmtlcl82ZDEyZGZjMmY4MTI0NDgzYjAwOGFiM2Q1NGQzMmRiNSA9IEwubWFya2VyKAogICAgICAgICAgICAgICAgWy0zNC42MDM3LC01OC4zODE2XSwKICAgICAgICAgICAgICAgIHsKICAgICAgICAgICAgICAgICAgICBpY29uOiBuZXcgTC5JY29uLkRlZmF1bHQoKQogICAgICAgICAgICAgICAgICAgIH0KICAgICAgICAgICAgICAgICkKICAgICAgICAgICAgICAgIC5hZGRUbyhtYXBfY2U2MjdkYTU4MmFjNDg3ZjljZTdmOGQyZDZlMTE1NTApOwogICAgICAgICAgICAKPC9zY3JpcHQ+" style="position:absolute;width:100%;height:100%;left:0;top:0;border:none !important;" allowfullscreen webkitallowfullscreen mozallowfullscreen></iframe></div></div>



Great! Note that both the map object and the map marker are just stored as variables.


```python
buenos_marker
```




    <folium.map.Marker at 0x1137d1d68>



And just like any other piece of
data in Python, we can place this marker in a list, and then retrieve it from the list.


```python
buenos_markers = [buenos_marker]
```


```python
buenos_markers[0]
```




    <folium.map.Marker at 0x1137d1d68>



Here are some other markers to add to our map:


```python
neighborhood_markers = ['Palermo', 'Ricoleta', 'Santelmo', 'Puerto Madero', 'Belgrano', 'La Boca']
marker_one = folium.Marker([-34.5711, -58.4233])
marker_two = folium.Marker([-34.5895, -58.3974])
marker_three = folium.Marker([-34.6212, -58.3731])
marker_four = folium.Marker([-34.6177, -58.3621])
marker_five = folium.Marker([-34.43,  -58.32])
marker_six = folium.Marker([-34.6345, -58.3631])
neighborhood_markers = [marker_one, marker_two, marker_three, marker_four, marker_five, marker_six]
```

Select the last marker and assign it equal to `la_boca_marker`.


```python
la_boca_marker = None
```


```python
import folium
buenos_map = folium.Map([-34.6037, -58.3816], zoom_start = 13)
la_boca_marker.add_to(buenos_map)
buenos_map
```

Now that we plotted `la_boca` we don't need the marker anymore.  So remove this last element from our `neighborhood_markers` list.


```python
neighborhood_markers.pop()
```


```python
len(neighborhood_markers) # 6
neighborhood_markers[-1] == marker_five # True
```

Now select the second marker in the list and set that equal to `recoleta`.


```python
recoleta = None
```


```python
buenos_map = folium.Map([-34.6037, -58.3816], zoom_start = 13)
recoleta.add_to(buenos_map)
buenos_map
```

Don't worry if this feels tedious and manual. When we get up to loops in Python, we will see how to easily plot all of the markers in our list.


```python
for marker in neighborhood_markers:
    marker.add_to(buenos_map)
buenos_map
```

But that's a lesson for another day.

### Summary

In this lesson we saw how to select information from a list and then plot that information with maps.  We saw that lists can make good arguments to methods, as they represent an ordered collection of information, like latitude followed by longitude.  In just a few lessons we saw how to use Python to make visualizations with our data going forward.
