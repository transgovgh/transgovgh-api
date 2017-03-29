### Get all regions

`Endpoint: GET https://api.example.org/api/v1.0/regions/`

 ``Response: 200 ok``

     [
      {
        "id": 1,
        "region": "Greater Accra",
        "author": 1,
        "created_date": "2017-03-29T09:42:47.763945Z",
        "modified": "2017-03-29T09:42:47.763970Z"
      }
    ]

### Get all suburbs

`Endpoint: GET https://api.example.org/api/v1.0/suburbs/`

 ``Response: 200 ok``

     [
      {
        "id": 1,
        "region": {
          "id": 1,
          "region": "Greater Accra",
          "author": 1,
          "created_date": "2017-03-29T09:42:47.763945Z",
          "modified": "2017-03-29T09:42:47.763970Z"
        },
        "suburb": "Abeka",
        "author": 1,
        "created_date": "2017-03-29T09:43:07.583824Z",
        "modified": "2017-03-29T09:43:07.583849Z"
      }
    ]
