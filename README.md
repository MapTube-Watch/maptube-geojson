# MAPTUBE-JSON

>json format of maptube

****************

### OVERALL JSON FORMAT

```
{
    "video_metadata": {
        "author": {
            "first_name": "STRING",
            "middle_name": "STRING",
            "last_name": "STRING",
            "email": "STRING",
            "username": "STRING"
        },
        "properties": {
            "title": "STRING",
            "description": "STRING",
            "duration": INTEGER (IN SECONDS),
            "created": INTEGER UNIX TIMESTAMP,
            "source": [
                "STRING URL", 
                "STRING URL",
                ...
            ],
            "keyword": [
                "STRING", 
                "STRING", 
                ...
            ]
        }
    },
    "video_data": [
        __SINGLE FRAME FORMAT__,
        __SINGLE FRAME FORMAT__,
        ...
    ]
}
```

#### SINGLE FRAME FORMAT

```
{
    "frame": INTEGER (IN INCREMENT),
    "description": "STRING",
    "duration": INTEGER (IN SECONDS),
    "basemap_style": "MAPBOX STYLE",
    "basemap_center_coord": [DOUBLE LATITUDE, DOUBLE LONGITUDE],
    "basemap_zoom": INTEGER,
    "geojson": {
        "type": "FeatureCollection",
        "features": [
        {
            "type": "Feature",
            "properties": {
                "title": "STRING",
                "description": "STRING",
                "duration": INTEGER (IN SECONDS TO STAY),
                "source": [
                    "STRING URL", 
                    "STRING URL",
                    ...
                ],
                "keyword": [
                    "STRING", 
                    "STRING", 
                    ...
                ]
            },
            "geometry": {
            "type": "GeometryCollection",
            "geometries": [
                __INDIVIDUAL FEATURE__,
                __INDIVIDUAL FEATURE__,
                ...
            ]
            }
        }
        ]
    }
}
```

#### INDIVIDUAL FEATURE

1. POINT

```
{
    "type": "Point",
    "properties": {
        "style": {
            "color": HTML COLOR CODE,
            "thickness": INTEGER
        },
        "title": "STRING",
        "description": "STRING",
        "source": [
            "STRING URL", 
            "STRING URL",
            ...
        ],
        "keyword": [
            "STRING", 
            "STRING", 
            ...
        ]
    }
    "coordinates": [DOUBLE LATITUDE, DOUBLE LONGITUDE]
}
```

2. LINESTRING

```
{
    "type": "LineString",
    "properties": {
        "style": {
            "color": HTML COLOR CODE,
            "thickness": INTEGER
        },
        "title": "STRING",
        "description": "STRING",
        "source": [
            "STRING URL", 
            "STRING URL",
            ...
        ],
        "keyword": [
            "STRING", 
            "STRING", 
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

3. POLYGON

```
{
    "type": "Polygon",
    "properties": {
        "style": {
            "color": HTML COLOR CODE,
            "thickness": INTEGER
        },
        "title": "STRING",
        "description": "STRING",
        "source": [
            "STRING URL", 
            "STRING URL",
            ...
        ],
        "keyword": [
            "STRING", 
            "STRING", 
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

4. MULTIPOINT

```
{
    "type": "MultiPoint",
    "properties": {
        "style": {
            "color": HTML COLOR CODE,
            "thickness": INTEGER
        },
        "title": "STRING",
        "description": "STRING",
        "source": [
            "STRING URL", 
            "STRING URL",
            ...
        ],
        "keyword": [
            "STRING", 
            "STRING", 
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

5. MULTILINESTRING

```
{
    "type": "MultiLineString",
    "properties": {
        "style": {
            "color": HTML COLOR CODE,
            "thickness": INTEGER
        },
        "title": "STRING",
        "description": "STRING",
        "source": [
            "STRING URL", 
            "STRING URL",
            ...
        ],
        "keyword": [
            "STRING", 
            "STRING", 
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

6. MULTIPOLYGON

```
{
    "type": "MultiPolygon",
    "properties": {
        "style": {
            "color": HTML COLOR CODE,
            "thickness": INTEGER
        },
        "title": "STRING",
        "description": "STRING",
        "source": [
            "STRING URL", 
            "STRING URL",
            ...
        ],
        "keyword": [
            "STRING", 
            "STRING", 
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