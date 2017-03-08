### Overview

This is where a user can report or post any incident in his area, being it water spillage, public toilet spillage etc. The post is done by category. This page shows how a user can do the posting via mobile app

### Get all Case categories

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

### Create a case
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
              "location": "Ablekuma North Sub Metro"
              }

  - Response: ``201 Created``

          {
            "id": 13,
            "case_number": "9BCA763349",
            "case_category": {
            "id": 2,
            "category_name": "Water",
            "description": "This in information about water works",
            "category_image": "/media/images/category_image.jpg",
            "author": 1
          },
          "case_name": "Another case by user",
          "case_description": "This is to test if it would separate user again",
          "case_image_one": "/media/images/about-1-pict.jpg",
          "case_image_two": "/media/images/about-2-pict.jpg",
          "case_image_three": "/media/images/about-3-pict.jpg",
          "case_status": "fixing",
          "location": "Ablekuma North Sub Metro",
          "author": 2,
          "gravity": false,
          "count_gravity": 0,
          "created_date": "2017-02-21T16:21:22.661830Z"
          }


### Update a case

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
            "location": "Ablekuma North Sub Metro"
            }

  - Response: ``201 Created``

        {
            "id": 13,
            "case_number": "9BCA763349",
            "case_category": {
            "id": 2,
            "category_name": "Water",
            "description": "This in information about water works",
            "category_image": "/media/images/category_image.jpg",
            "author": 1
          },
          "case_name": "Another case by user",
          "case_description": "This is to test if it would separate user again",
          "case_image_one": "/media/images/about-1-pict.jpg",
          "case_image_two": "/media/images/about-2-pict.jpg",
          "case_image_three": "/media/images/about-3-pict.jpg",
          "case_status": "fixing",
          "location": "Ablekuma North Sub Metro",
          "author": 2,
          "gravity": false,
          "count_gravity": 0,
          "created_date": "2017-02-21T16:21:22.661830Z"
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
### Add gravity to project 
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
        }


### Get all cases 
The project results on this page are paginated
- Method: `POST`

- Endpoint:  `https://api.example.org/api/v1.0/project-case/`

 - Response: ``200 ok``

        {
          "count": 13,
          "next": "http://localhost:8000/api/v1.0/project-case/?page=2",
          "previous": null,
          "results": [
            {
              "id": 2,
              "case_number": null,
              "case_category": {
                "id": 2,
                "category_name": "Water",
                "description": "This in information about water works",
                "author": 1
              },
              "case_name": "Lights out",
              "case_description": "This a case about a broken pipe in my hood",
              "case_image": "http://localhost:8000/media/images/vlcsnap-2015-08-28-20h54m02s198_zbGNamp.jpg",
              "case_status": "Pending",
              "location": "Ablekuma North Sub Metro",
              "author": 1,
              "gravity": false,
              "count_gravity": 0,
              "created_date": "2017-02-06T18:38:35.611770Z",
              "case_images": []
            },
            {
              "id": 4,
              "case_number": "8B6F3E7894",
              "case_category": {
                "id": 1,
                "category_name": "Electricity",
                "description": "This is information about electricity",
                "author": 1
              },
              "case_name": "water problem",
              "case_description": "This a case about a spilling pipe in my hood",
              "case_image": "http://localhost:8000/media/images/vlcsnap-2015-08-28-20h54m02s198_boDq2WE.jpg",
              "case_status": "Pending",
              "location": "Ablekuma North Sub Metro",
              "author": 1,
              "gravity": false,
              "count_gravity": 0,
              "created_date": "2017-02-06T18:51:36.549951Z",
              "case_images": []
            },
            {
              "id": 5,
              "case_number": "E53ED6AFAF",
              "case_category": {
                "id": 2,
                "category_name": "Water",
                "description": "This in information about water works",
                "author": 1
              },
              "case_name": "Electric Problem in the hood",
              "case_description": "This a case about a spilling pipe in my hood",
              "case_image": "http://localhost:8000/media/images/vlcsnap-2015-08-28-20h54m02s198_uJjADHr.jpg",
              "case_status": "Pending",
              "location": "Ablekuma North Sub Metro",
              "author": 1,
              "gravity": false,
              "count_gravity": 0,
              "created_date": "2017-02-06T18:52:04.272207Z",
              "case_images": []
            }
          ]
        }



### Get all cases a user has reported 

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
          }
        ]

### Get all reported cases but Pending 
- (pending cases)

- Method: `GET`

- Endpoint: `https://api.example.org/api/v1.0/project-case/pending-cases/`

- User Authorization: ``Required`` 

          "Authorization": "Token xxxxxxxxxxxxx"

 - Response: ``200 ok``

        [
          {
            "id": 6,
            "case_number": "076ABF9C2A",
            "case_category": {
              "id": 1,
              "category_name": "Electricity",
              "description": "This is information about electricity",
              "author": 1
            },
            "case_name": "Electric Problem Edited",
            "case_description": "This a case about a spilling pipe in my hood working",
            "case_image": "/media/images/vlcsnap-2015-08-28-20h54m02s198_b4WBJNp.jpg",
            "case_status": "pending",
            "location": "Ablekuma North Sub Metro",
            "author": 1,
            "gravity": false,
            "count_gravity": 0,
            "created_date": "2017-02-06T21:00:21.810506Z",
            "case_images": [
              {
                "id": 14,
                "case_images": "/media/images/vvvvvv_aSSrKIH.jpg"
              },
              {
                "id": 13,
                "case_images": "/media/images/vvvvvv_3YkiZck.jpg"
              },
              {
                "id": 12,
                "case_images": "/media/images/vvvvvv_eVJrm9F.jpg"
              }
            ]
          },
          {
            "id": 7,
            "case_number": "ECEFC3C994",
            "case_category": {
              "id": 1,
              "category_name": "Electricity",
              "description": "This is information about electricity",
              "author": 1
            },
            "case_name": "New case with Email sending",
            "case_description": "This a case about a spilling pipe in my hood working",
            "case_image": "/media/images/vlcsnap-2015-08-28-20h54m02s198_1avGDJV.jpg",
            "case_status": "pending",
            "location": "Ablekuma North Sub Metro",
            "author": 1,
            "gravity": false,
            "count_gravity": 0,
            "created_date": "2017-02-07T16:45:40.347612Z",
            "case_images": []
          }
        ]


### Get all reported cases and being fixed by duty bearers 

- (fixing cases)

- Method: `GET`

- Endpoint:  `https://api.example.org/api/v1.0/project-case/fixing-cases/`

 - Response: ``200 ok``

        [
          {
            "id": 9,
            "case_number": "BAF202610D",
            "case_category": {
              "id": 1,
              "category_name": "Electricity",
              "description": "This is information about electricity",
              "author": 1
            },
            "case_name": "New case with Email sending 2",
            "case_description": "This a case about a spilling pipe in my hood working",
            "case_image": "/media/images/vlcsnap-2015-08-28-20h54m02s198_FPKSI7A.jpg",
            "case_status": "fixing",
            "location": "Ablekuma North Sub Metro",
            "author": 1,
            "gravity": false,
            "count_gravity": 0,
            "created_date": "2017-02-07T21:25:25.794459Z",
            "case_images": []
          },
          {
            "id": 3,
            "case_number": "8308B0F085",
            "case_category": {
              "id": 2,
              "category_name": "Water",
              "description": "This in information about water works",
              "author": 1
            },
            "case_name": "Lights out",
            "case_description": "This a case about a broken pipe in my hood",
            "case_image": "/media/images/vlcsnap-2015-08-28-20h54m02s198_WI0V1bk.jpg",
            "case_status": "fixing",
            "location": "Ablekuma North Sub Metro",
            "author": 1,
            "gravity": false,
            "count_gravity": 0,
            "created_date": "2017-02-06T18:51:11.318925Z",
            "case_images": []
          },
          {
            "id": 8,
            "case_number": "7BBD57D1FE",
            "case_category": {
              "id": 1,
              "category_name": "Electricity",
              "description": "This is information about electricity",
              "author": 1
            },
            "case_name": "New case with Email sending",
            "case_description": "This a case about a spilling pipe in my hood working",
            "case_image": "/media/images/vlcsnap-2015-08-28-20h54m02s198_xLpNf36.jpg",
            "case_status": "fixing",
            "location": "Ablekuma North Sub Metro",
            "author": 1,
            "gravity": false,
            "count_gravity": 0,
            "created_date": "2017-02-07T16:46:19.856830Z",
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
          }
        ]


### Get all fixed cases 

- (fixed cases)

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
              "author": 1
            },
            "case_name": "Lights out",
            "case_description": "This a case about a broken pipe in my hood",
            "case_image": "/media/images/vlcsnap-2015-08-28-20h54m02s198_GmMvSGy.jpg",
            "case_status": "case_fixed",
            "location": "Ablekuma North Sub Metro",
            "author": 1,
            "gravity": false,
            "count_gravity": 0,
            "created_date": "2017-02-06T18:32:47.413277Z",
            "case_images": []
          }
        ]
