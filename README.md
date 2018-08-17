# MAPTUBE-JSON

json format for maptube

****************

#### OVERALL JSON FORMAT

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

#### __SINGLE_FRAME_FORMAT__

```javascript
{
    "frame": INTEGER IN INCREMENT,
    "description": STRING,
    "duration": INTEGER IN SECONDS TO STAY,
    "basemap_style": MAPBOX STYLE,
    "basemap_center_coord": [DOUBLE LATITUDE, DOUBLE LONGITUDE],
    "basemap_zoom": INTEGER,
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
    }
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

#### __FEATURE_COLLECTION__

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
            __INDIVIDUAL_FEATURE__,
            __INDIVIDUAL_FEATURE__,
            ...
        ]
    }
}
```

#### __INDIVIDUAL_FEATURE__

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
    }
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
    }
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
    }
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
    }
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
    }
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
    }
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