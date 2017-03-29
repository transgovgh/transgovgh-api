### Overview

This is where a user can report or post any incident in his area, being it water spillage, public toilet spillage etc. The post is done by category. This page shows how a user can do the posting via mobile app

### Get all fault categories

- Method: `GET`

- Endpoint: `https://api.example.org/api/v1.0/case-category`

  - Response: `201 Created`

        [
          {
            "id": 1,
            "category_name": "Electricity",
            "description": "This is information about electricity",
            "category_image": "/media/images/category_image.jpg",
            "author": 1
          },
          {
            "id": 2,
            "category_name": "Water",
            "description": "This in information about water works",
            "category_image": "/media/images/category_image.jpg",
            "author": 1
          }
        ]

### Report a fault
- Method:`POST`

- Endpoint: `https://api.example.org/api/v1.0/project-case/create-case/`

- User Authorization: ``Required`` 

          "Authorization": "Token xxxxxxxxxxxxx"

  - Request: ``[JSON Body]``

    - Note: ``case_image_one``, ``case_image_two``, ``case_image_two`` are all file field

              {
              "case_category": 2,
              "case_name": "Another case by user",
              "case_description": "This is to test if it would separate user again",
              "case_image_one": "/home/eit/Pictures/test.jpg",
              "case_image_two": "/home/eit/Pictures/test.jpg",
              "case_image_three": "/home/eit/Pictures/test.jpg",
              "case_status": "fixing",
              "region": 1,
              "suburb": 1,
              "land_mark": "close to school junction, Ashale botwe"
              }

  - Response: ``201 Created``

          {
            "status_code": 201,
            "message": "You have updated a fault reported",
            "results": {
              "id": 45,
              "case_number": "7F794850FC",
              "case_category": {
                "id": 2,
                "category_name": "Water",
                "description": "This in information about water works",
                "category_image": null,
                "author": 1
              },
              "case_name": "Test region and suburb",
              "case_description": "This is to test if it would separate user again",
              "case_image_one": "/home/eit/Pictures/test.jpg",
              "case_image_two": "/home/eit/Pictures/test.jpg",
              "case_image_three": "/home/eit/Pictures/test.jpg",
              "case_status": "pending",
              "region": {
                "id": 1,
                "region": "Greater Accra",
                "author": 1,
                "created_date": "2017-03-28T13:47:27.384510Z",
                "modified": "2017-03-28T13:47:27.384535Z"
              },
              "suburb": {
                "id": 1,
                "region": 1,
                "suburb": "Abeka",
                "author": 1,
                "created_date": "2017-03-28T13:47:41.793889Z",
                "modified": "2017-03-28T13:47:41.793925Z"
              },
              "land_mark": "close to school junction, Ashale botwe",
              "author": 1,
              "gravity": false,
              "count_gravity": 0,
              "created_date": "2017-03-28T22:36:18.637705Z"
            }
          }


### Update a fault

- Method: `POST`

- Endpoint: `https://api.example.org/api/v1.0/project-case/{xx}/update-case/`

- User Authorization: ``Required`` 

          "Authorization": "Token xxxxxxxxxxxxx"

  - Request: ``[JSON Body]``

      - Note: ``case_image_one``, ``case_image_two``, ``case_image_two`` are all file field


            {
            "case_category": 2,
            "case_name": "Another case by user",
            "case_description": "This is to test if it would separate user again",
            "case_image_one": "/home/eit/Pictures/test.jpg",
            "case_image_two": "/home/eit/Pictures/test.jpg",
            "case_image_three": "/home/eit/Pictures/test.jpg",
            "case_status": "fixing",
            "region": 1,
            "suburb": 1,
            "land_mark": "close to school junction, Ashale botwe"
            }

  - Response: ``201 Created``

        {
          "status_code": 201,
          "message": "You have updated a fault reported",
          "results": {
            "id": 45,
            "case_number": "7F794850FC",
            "case_category": {
              "id": 2,
              "category_name": "Water",
              "description": "This in information about water works",
              "category_image": null,
              "author": 1
            },
            "case_name": "Test region and suburb",
            "case_description": "This is to test if it would separate user again",
            "case_image_one": "/home/eit/Pictures/test.jpg",
            "case_image_two": "/home/eit/Pictures/test.jpg",
            "case_image_three": "/home/eit/Pictures/test.jpg",
            "case_status": "pending",
            "region": {
              "id": 1,
              "region": "Greater Accra",
              "author": 1,
              "created_date": "2017-03-28T13:47:27.384510Z",
              "modified": "2017-03-28T13:47:27.384535Z"
            },
            "suburb": {
              "id": 1,
              "region": 1,
              "suburb": "Abeka",
              "author": 1,
              "created_date": "2017-03-28T13:47:41.793889Z",
              "modified": "2017-03-28T13:47:41.793925Z"
            },
            "land_mark": "close to school junction, Ashale botwe",
            "author": 1,
            "gravity": false,
            "count_gravity": 0,
            "created_date": "2017-03-28T22:36:18.637705Z"
          }
        }

<!-- 
### Add images to a case

`Endpoint: POST https://api.example.org/api/v1.0/project-case/{pk}/add-images/`

  ``Request: [JSON Body]``

    {
    "case_images": "/media/images/about-1-pict.jpg",
    }

  `Response: 201 Created`

    {
    "id": 1,
    "case_images": "/media/images/about-1-pict.jpg",
    }
 -->
### Add gravity to fault reported (upvote)
This is to show how serious reported the case is

- Method: `POST`

- Endpoint:  `https://api.example.org/api/v1.0/project-case/{pk}/add-gravity/`

- User Authorization: ``Required`` 

          "Authorization": "Token xxxxxxxxxxxxx"

  - Response: `201 Created`

        {
          "id": 13,
          "case_number": "9BCA763349",
          "case_category": {
              "id": 2,
              "category_name": "Water",
              "description": "This in information about water works",
              "category_image": null,
              "author": 1
            },
            "case_name": "Test region and suburb",
            "case_description": "This is to test if it would separate user again",
            "case_image_one": "/home/eit/Pictures/test.jpg",
            "case_image_two": "/home/eit/Pictures/test.jpg",
            "case_image_three": "/home/eit/Pictures/test.jpg",
            "case_status": "pending",
            "region": {
              "id": 1,
              "region": "Greater Accra",
              "author": 1,
              "created_date": "2017-03-28T13:47:27.384510Z",
              "modified": "2017-03-28T13:47:27.384535Z"
            },
            "suburb": {
              "id": 1,
              "region": 1,
              "suburb": "Abeka",
              "author": 1,
              "created_date": "2017-03-28T13:47:41.793889Z",
              "modified": "2017-03-28T13:47:41.793925Z"
            },
            "land_mark": "close to school junction, Ashale botwe",
            "author": 1,
            "gravity": false,
            "count_gravity": 0,
            "created_date": "2017-03-28T22:36:18.637705Z"
          "case_images": [
            {
              "id": 17,
              "case_images": "/media/images/about-1-pict_m1FD6Pf.jpg"
            },
            {
              "id": 16,
              "case_images": "/media/images/about-1-pict_0E8hVN6.jpg"
            },
            {
              "id": 15,
              "case_images": "/media/images/about-1-pict_wpo22JP.jpg"
            }
          ]
        }


### Get all faults reported 
The project results on this page are paginated
- Method: `GET`

- Endpoint:  `https://api.example.org/api/v1.0/project-case/`

 - Response: ``200 ok``

        {
          "id": 13,
          "case_number": "9BCA763349",
          "case_category": {
              "id": 2,
              "category_name": "Water",
              "description": "This in information about water works",
              "category_image": null,
              "author": 1
            },
            "case_name": "Test region and suburb",
            "case_description": "This is to test if it would separate user again",
            "case_image_one": "/home/eit/Pictures/test.jpg",
            "case_image_two": "/home/eit/Pictures/test.jpg",
            "case_image_three": "/home/eit/Pictures/test.jpg",
            "case_status": "pending",
            "region": {
              "id": 1,
              "region": "Greater Accra",
              "author": 1,
              "created_date": "2017-03-28T13:47:27.384510Z",
              "modified": "2017-03-28T13:47:27.384535Z"
            },
            "suburb": {
              "id": 1,
              "region": 1,
              "suburb": "Abeka",
              "author": 1,
              "created_date": "2017-03-28T13:47:41.793889Z",
              "modified": "2017-03-28T13:47:41.793925Z"
            },
            "land_mark": "close to school junction, Ashale botwe",
            "author": 1,
            "gravity": false,
            "count_gravity": 0,
            "created_date": "2017-03-28T22:36:18.637705Z"
          "case_images": [
            {
              "id": 17,
              "case_images": "/media/images/about-1-pict_m1FD6Pf.jpg"
            },
            {
              "id": 16,
              "case_images": "/media/images/about-1-pict_0E8hVN6.jpg"
            },
            {
              "id": 15,
              "case_images": "/media/images/about-1-pict_wpo22JP.jpg"
            }
          ]
        }



### Get all faults a user has reported 

 - (my cases)

- Method: `GET`

- Endpoint: `https://api.example.org/api/v1.0/project-case/my-cases/`

- User Authorization: ``Required`` 

          "Authorization": "Token xxxxxxxxxxxxx"

 - Response: ``200 ok``

        [
          {
            "id": 11,
            "case_number": "CC245B8C06",
            "case_category": {
              "id": 2,
              "category_name": "Water",
              "description": "This in information about water works",
              "author": 1
            },
            "case_name": "User created this case",
            "case_description": "This is to test if it would separate user",
            "case_image": "/media/images/vvvvvv_CuW36e6.jpg",
            "case_status": "pending",
            "location": "Ablekuma North Sub Metro",
            "author": 2,
            "gravity": false,
            "count_gravity": 0,
            "created_date": "2017-02-07T22:18:37.582209Z",
            "case_images": []
          },
          {
            "id": 13,
            "case_number": "9BCA763349",
            "case_category": {
              "id": 2,
              "category_name": "Water",
              "description": "This in information about water works",
              "author": 1
            },
            "case_name": "Another case by user",
            "case_description": "This is to test if it would separate user again",
            "case_image": "/media/images/about-1-pict.jpg",
            "case_status": "fixing",
            "location": "Ablekuma North Sub Metro",
            "author": 2,
            "gravity": true,
            "count_gravity": 1,
            "created_date": "2017-02-21T16:21:22.661830Z",
            "case_images": [
              {
                "id": 17,
                "case_images": "/media/images/about-1-pict_m1FD6Pf.jpg"
              },
              {
                "id": 16,
                "case_images": "/media/images/about-1-pict_0E8hVN6.jpg"
              },
              {
                "id": 15,
                "case_images": "/media/images/about-1-pict_wpo22JP.jpg"
              }
            ]
          },
          {
          "id": 13,
          "case_number": "9BCA763349",
          "case_category": {
              "id": 2,
              "category_name": "Water",
              "description": "This in information about water works",
              "category_image": null,
              "author": 1
            },
            "case_name": "Test region and suburb",
            "case_description": "This is to test if it would separate user again",
            "case_image_one": "/home/eit/Pictures/test.jpg",
            "case_image_two": "/home/eit/Pictures/test.jpg",
            "case_image_three": "/home/eit/Pictures/test.jpg",
            "case_status": "pending",
            "region": {
              "id": 1,
              "region": "Greater Accra",
              "author": 1,
              "created_date": "2017-03-28T13:47:27.384510Z",
              "modified": "2017-03-28T13:47:27.384535Z"
            },
            "suburb": {
              "id": 1,
              "region": 1,
              "suburb": "Abeka",
              "author": 1,
              "created_date": "2017-03-28T13:47:41.793889Z",
              "modified": "2017-03-28T13:47:41.793925Z"
            },
            "land_mark": "close to school junction, Ashale botwe",
            "author": 1,
            "gravity": false,
            "count_gravity": 0,
            "created_date": "2017-03-28T22:36:18.637705Z"
          "case_images": [
            {
              "id": 17,
              "case_images": "/media/images/about-1-pict_m1FD6Pf.jpg"
            },
            {
              "id": 16,
              "case_images": "/media/images/about-1-pict_0E8hVN6.jpg"
            },
            {
              "id": 15,
              "case_images": "/media/images/about-1-pict_wpo22JP.jpg"
            }
          ]
        }
        ]

### Get all reported faults but Pending 
- (pending faults)

- Method: `GET`

- Endpoint: `https://api.example.org/api/v1.0/project-case/pending-cases/`

- User Authorization: ``Required`` 

          "Authorization": "Token xxxxxxxxxxxxx"

 - Response: ``200 ok``

        [
          {
            "id": 11,
            "case_number": "CC245B8C06",
            "case_category": {
              "id": 2,
              "category_name": "Water",
              "description": "This in information about water works",
              "author": 1
            },
            "case_name": "User created this case",
            "case_description": "This is to test if it would separate user",
            "case_image": "/media/images/vvvvvv_CuW36e6.jpg",
            "case_status": "pending",
            "location": "Ablekuma North Sub Metro",
            "author": 2,
            "gravity": false,
            "count_gravity": 0,
            "created_date": "2017-02-07T22:18:37.582209Z",
            "case_images": []
          },
          {
            "id": 13,
            "case_number": "9BCA763349",
            "case_category": {
              "id": 2,
              "category_name": "Water",
              "description": "This in information about water works",
              "author": 1
            },
            "case_name": "Another case by user",
            "case_description": "This is to test if it would separate user again",
            "case_image": "/media/images/about-1-pict.jpg",
            "case_status": "pending",
            "location": "Ablekuma North Sub Metro",
            "author": 2,
            "gravity": true,
            "count_gravity": 1,
            "created_date": "2017-02-21T16:21:22.661830Z",
            "case_images": [
              {
                "id": 17,
                "case_images": "/media/images/about-1-pict_m1FD6Pf.jpg"
              },
              {
                "id": 16,
                "case_images": "/media/images/about-1-pict_0E8hVN6.jpg"
              },
              {
                "id": 15,
                "case_images": "/media/images/about-1-pict_wpo22JP.jpg"
              }
            ]
          },
          {
          "id": 13,
          "case_number": "9BCA763349",
          "case_category": {
              "id": 2,
              "category_name": "Water",
              "description": "This in information about water works",
              "category_image": null,
              "author": 1
            },
            "case_name": "Test region and suburb",
            "case_description": "This is to test if it would separate user again",
            "case_image_one": "/home/eit/Pictures/test.jpg",
            "case_image_two": "/home/eit/Pictures/test.jpg",
            "case_image_three": "/home/eit/Pictures/test.jpg",
            "case_status": "pending",
            "region": {
              "id": 1,
              "region": "Greater Accra",
              "author": 1,
              "created_date": "2017-03-28T13:47:27.384510Z",
              "modified": "2017-03-28T13:47:27.384535Z"
            },
            "suburb": {
              "id": 1,
              "region": 1,
              "suburb": "Abeka",
              "author": 1,
              "created_date": "2017-03-28T13:47:41.793889Z",
              "modified": "2017-03-28T13:47:41.793925Z"
            },
            "land_mark": "close to school junction, Ashale botwe",
            "author": 1,
            "gravity": false,
            "count_gravity": 0,
            "created_date": "2017-03-28T22:36:18.637705Z"
          "case_images": [
            {
              "id": 17,
              "case_images": "/media/images/about-1-pict_m1FD6Pf.jpg"
            },
            {
              "id": 16,
              "case_images": "/media/images/about-1-pict_0E8hVN6.jpg"
            },
            {
              "id": 15,
              "case_images": "/media/images/about-1-pict_wpo22JP.jpg"
            }
          ]
        }
        ]


### Get all reported faults and being fixed by duty bearers 

- (fixing faults)

- Method: `GET`

- Endpoint:  `https://api.example.org/api/v1.0/project-case/fixing-cases/`

 - Response: ``200 ok``

        [
          {
            "id": 11,
            "case_number": "CC245B8C06",
            "case_category": {
              "id": 2,
              "category_name": "Water",
              "description": "This in information about water works",
              "author": 1
            },
            "case_name": "User created this case",
            "case_description": "This is to test if it would separate user",
            "case_image": "/media/images/vvvvvv_CuW36e6.jpg",
            "case_status": "fixing",
            "location": "Ablekuma North Sub Metro",
            "author": 2,
            "gravity": false,
            "count_gravity": 0,
            "created_date": "2017-02-07T22:18:37.582209Z",
            "case_images": []
          },
          {
            "id": 13,
            "case_number": "9BCA763349",
            "case_category": {
              "id": 2,
              "category_name": "Water",
              "description": "This in information about water works",
              "author": 1
            },
            "case_name": "Another case by user",
            "case_description": "This is to test if it would separate user again",
            "case_image": "/media/images/about-1-pict.jpg",
            "case_status": "fixing",
            "location": "Ablekuma North Sub Metro",
            "author": 2,
            "gravity": true,
            "count_gravity": 1,
            "created_date": "2017-02-21T16:21:22.661830Z",
            "case_images": [
              {
                "id": 17,
                "case_images": "/media/images/about-1-pict_m1FD6Pf.jpg"
              },
              {
                "id": 16,
                "case_images": "/media/images/about-1-pict_0E8hVN6.jpg"
              },
              {
                "id": 15,
                "case_images": "/media/images/about-1-pict_wpo22JP.jpg"
              }
            ]
          },
          {
          "id": 13,
          "case_number": "9BCA763349",
          "case_category": {
              "id": 2,
              "category_name": "Water",
              "description": "This in information about water works",
              "category_image": null,
              "author": 1
            },
            "case_name": "Test region and suburb",
            "case_description": "This is to test if it would separate user again",
            "case_image_one": "/home/eit/Pictures/test.jpg",
            "case_image_two": "/home/eit/Pictures/test.jpg",
            "case_image_three": "/home/eit/Pictures/test.jpg",
            "case_status": "fixing",
            "region": {
              "id": 1,
              "region": "Greater Accra",
              "author": 1,
              "created_date": "2017-03-28T13:47:27.384510Z",
              "modified": "2017-03-28T13:47:27.384535Z"
            },
            "suburb": {
              "id": 1,
              "region": 1,
              "suburb": "Abeka",
              "author": 1,
              "created_date": "2017-03-28T13:47:41.793889Z",
              "modified": "2017-03-28T13:47:41.793925Z"
            },
            "land_mark": "close to school junction, Ashale botwe",
            "author": 1,
            "gravity": false,
            "count_gravity": 0,
            "created_date": "2017-03-28T22:36:18.637705Z"
          "case_images": [
            {
              "id": 17,
              "case_images": "/media/images/about-1-pict_m1FD6Pf.jpg"
            },
            {
              "id": 16,
              "case_images": "/media/images/about-1-pict_0E8hVN6.jpg"
            },
            {
              "id": 15,
              "case_images": "/media/images/about-1-pict_wpo22JP.jpg"
            }
          ]
        }
        ]


### Get all fixed faults reported 

- (fixed faults)

- Method: `GET`

- Endpoint: `https://api.example.org/api/v1.0/project-case/fixed-cases/`

 - Response: ``200 ok``
 
        [
          {
            "id": 1,
            "case_number": "CABBC28380",
            "case_category": {
              "id": 2,
              "category_name": "Water",
              "description": "This in information about water works",
              "category_image": null,
              "author": 1
            },
            "case_name": "Test region and suburb",
            "case_description": "This is to test if it would separate user again",
            "case_image_one": "/home/eit/Pictures/test.jpg",
            "case_image_two": "/home/eit/Pictures/test.jpg",
            "case_image_three": "/home/eit/Pictures/test.jpg",
            "case_status": "fixed",
            "region": {
              "id": 1,
              "region": "Greater Accra",
              "author": 1,
              "created_date": "2017-03-28T13:47:27.384510Z",
              "modified": "2017-03-28T13:47:27.384535Z"
            },
            "suburb": {
              "id": 1,
              "region": 1,
              "suburb": "Abeka",
              "author": 1,
              "created_date": "2017-03-28T13:47:41.793889Z",
              "modified": "2017-03-28T13:47:41.793925Z"
            },
            "land_mark": "close to school junction, Ashale botwe",
            "author": 1,
            "gravity": false,
            "count_gravity": 0,
            "created_date": "2017-03-28T22:36:18.637705Z"
          "case_images": [
            {
              "id": 17,
              "case_images": "/media/images/about-1-pict_m1FD6Pf.jpg"
            },
            {
              "id": 16,
              "case_images": "/media/images/about-1-pict_0E8hVN6.jpg"
            },
            {
              "id": 15,
              "case_images": "/media/images/about-1-pict_wpo22JP.jpg"
            }
          ]
        ]
