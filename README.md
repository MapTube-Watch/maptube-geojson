# MAPTUBE-JSON

json format for maptube

****************

#### OVERALL JSON FORMAT

```JSON
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

```JSON
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

- POINT

```JSON
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

- LINESTRING

```JSON
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

- POLYGON

```JSON
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

- MULTIPOINT

```JSON
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

- MULTILINESTRING

```JSON
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

- MULTIPOLYGON

```JSON
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