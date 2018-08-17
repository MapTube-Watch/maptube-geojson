# MAPTUBE-JSON

json format for maptube

****************

#### OVERALL JSON FORMAT - Test it at [jsoneditoronline](https://jsoneditoronline.org/) and component structure is here 
![component.jpg](https://raw.githubusercontent.com/MapTube-Watch/maptube-json/master/docs/components.jpg "Frame, Feature Collection and Geometry Collection")


```javascript
{
    "video_metadata": {
        "author": {
            "first_name": STRING,
            "middle_name": STRING,
            "last_name": STRING,
            "email": STRING,
            "username": STRING
        },
        "properties": {
            "title": STRING,
            "description": STRING,
            "duration": INTEGER IN SECONDS,
            "created": INTEGER UNIX TIMESTAMP,
            "source": [
                STRING URL, 
                STRING URL,
                ...
            ],
            "keyword": [
                STRING, 
                STRING, 
                ...
            ]
        }
    },
    "video_data": [
        __SINGLE_FRAME_FORMAT__,
        __SINGLE_FRAME_FORMAT__,
        ...
    ]
}
```

#### \_\_SINGLE_FRAME_FORMAT\_\_

```javascript
{
    "frame": INTEGER IN INCREMENT,
    "properties": {
        "title": STRING,
        "description": STRING,
        "duration": INTEGER IN SECONDS TO STAY,
        "basemap_style": MAPBOX STYLE,
        "basemap_center_coord": [DOUBLE LATITUDE, DOUBLE LONGITUDE],
        "basemap_zoom": INTEGER,
        "source": [
            STRING URL, 
            STRING URL,
            ...
        ],
        "keyword": [
            STRING, 
            STRING, 
            ...
        ]
    },
    "geojson": {
        "type": "FeatureCollection",
        "features": [
            __FEATURE_COLLECTION__,
            __FEATURE_COLLECTION__,
            ...                         
        ]
    }
}
```

#### \_\_FEATURE_COLLECTION\_\_

```javascript
{
    "type": "Feature",
    "properties": {
        "title": STRING,
        "description": STRING,
        "source": [
            STRING URL, 
            STRING URL,
            ...
        ],
        "keyword": [
            STRING, 
            STRING, 
            ...
        ]
    },
    "geometry": {
        "type": "GeometryCollection",
        "geometries": [
            __GEOMETRY_COLLECTION__,
            __GEOMETRY_COLLECTION__,
            ...
        ]
    }
}
```

#### \_\_GEOMETRY_COLLECTION\_\_

#### List of Individual Geometries

- POINT

```javascript
{
    "type": "Point",
    "properties": {
        "style": {
            "color": HTML COLOR CODE,
            "thickness": INTEGER
        },
        "title": STRING,
        "description": STRING,
        "source": [
            STRING URL, 
            STRING URL,
            ...
        ],
        "keyword": [
            STRING, 
            STRING, 
            ...
        ]
    },
    "coordinates": [DOUBLE LATITUDE, DOUBLE LONGITUDE]
}
```

- LINESTRING

```javascript
{
    "type": "LineString",
    "properties": {
        "style": {
            "color": HTML COLOR CODE,
            "thickness": INTEGER
        },
        "title": STRING,
        "description": STRING,
        "source": [
            STRING URL, 
            STRING URL,
            ...
        ],
        "keyword": [
            STRING, 
            STRING, 
            ...
        ]
    },
    "coordinates": [
        [DOUBLE LATITUDE, DOUBLE LONGITUDE],
        [DOUBLE LATITUDE, DOUBLE LONGITUDE],
        ...
    ]
}
```

- POLYGON

```javascript
{
    "type": "Polygon",
    "properties": {
        "style": {
            "color": HTML COLOR CODE,
            "thickness": INTEGER
        },
        "title": STRING,
        "description": STRING,
        "source": [
            STRING URL, 
            STRING URL,
            ...
        ],
        "keyword": [
            STRING, 
            STRING, 
            ...
        ]
    },
    "coordinates": [
        [
            [DOUBLE LATITUDE, DOUBLE LONGITUDE],
            [DOUBLE LATITUDE, DOUBLE LONGITUDE],
            [DOUBLE LATITUDE, DOUBLE LONGITUDE],
            ...
        ]
    ]
}
```

- MULTIPOINT

```javascript
{
    "type": "MultiPoint",
    "properties": {
        "style": {
            "color": HTML COLOR CODE,
            "thickness": INTEGER
        },
        "title": STRING,
        "description": STRING,
        "source": [
            STRING URL, 
            STRING URL,
            ...
        ],
        "keyword": [
            STRING, 
            STRING, 
            ...
        ]
    },
    "coordinates": [
        [DOUBLE LATITUDE, DOUBLE LONGITUDE],
        [DOUBLE LATITUDE, DOUBLE LONGITUDE],
        ...
    ]
}
```

- MULTILINESTRING

```javascript
{
    "type": "MultiLineString",
    "properties": {
        "style": {
            "color": HTML COLOR CODE,
            "thickness": INTEGER
        },
        "title": STRING,
        "description": STRING,
        "source": [
            STRING URL, 
            STRING URL,
            ...
        ],
        "keyword": [
            STRING, 
            STRING, 
            ...
        ]
    },
    "coordinates": [
        [
            [DOUBLE LATITUDE, DOUBLE LONGITUDE],
            [DOUBLE LATITUDE, DOUBLE LONGITUDE],
            ...
        ],
        [
            [DOUBLE LATITUDE, DOUBLE LONGITUDE],
            [DOUBLE LATITUDE, DOUBLE LONGITUDE],
            ...
        ],
        ...
    ]
}
```

- MULTIPOLYGON

```javascript
{
    "type": "MultiPolygon",
    "properties": {
        "style": {
            "color": HTML COLOR CODE,
            "thickness": INTEGER
        },
        "title": STRING,
        "description": STRING,
        "source": [
            STRING URL, 
            STRING URL,
            ...
        ],
        "keyword": [
            STRING, 
            STRING, 
            ...
        ]
    },
    "coordinates": [
        [
            [
                [DOUBLE LATITUDE, DOUBLE LONGITUDE],
                [DOUBLE LATITUDE, DOUBLE LONGITUDE],
                [DOUBLE LATITUDE, DOUBLE LONGITUDE],
                ...
            ],
            [
                [DOUBLE LATITUDE, DOUBLE LONGITUDE],
                [DOUBLE LATITUDE, DOUBLE LONGITUDE],
                [DOUBLE LATITUDE, DOUBLE LONGITUDE],
                ...
            ],
            ...
        ],
        [
            [
                [DOUBLE LATITUDE, DOUBLE LONGITUDE],
                [DOUBLE LATITUDE, DOUBLE LONGITUDE],
                [DOUBLE LATITUDE, DOUBLE LONGITUDE],
                ...
            ],
            [
                [DOUBLE LATITUDE, DOUBLE LONGITUDE],
                [DOUBLE LATITUDE, DOUBLE LONGITUDE],
                [DOUBLE LATITUDE, DOUBLE LONGITUDE],
                ...
            ],
            ...
        ],
        ...
    ]
}
```