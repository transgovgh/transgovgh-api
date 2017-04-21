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
          "count": 19,
          "next": "http://stage.transgovgh.org/api/v1.0/project-case/?page=2",
          "previous": null,
          "results": [
            {
              "id": 64,
              "case_number": "74D8EDE842",
              "case_category": {
                "id": 5,
                "category_name": "Drainage",
                "description": "This is a category for drainage in Accra",
                "category_image": "https://transgovgh-stage.s3.amazonaws.com/images/category-drains.jpg",
                "author": 1
              },
              "case_name": "Broken teeth",
              "case_description": "My teeth are broken",
              "case_image_one": "https://transgovgh-stage.s3.amazonaws.com/case_image_one_folder/1492596642468b6ufv9liod4j478p0b1u7n5uc3IMG-20170419-WA0003.jpg",
              "case_image_two": "https://transgovgh-stage.s3.amazonaws.com/case_image_two_folder/1492596642468tk90kdqchla4i0p2nft5p62q69IMG-20170412-WA0013.jpg",
              "case_image_three": "https://transgovgh-stage.s3.amazonaws.com/case_image_three_folder/1492596642468m9m5vk6shnir7dulhvfjh2m3q0IMG-20170328-WA0011.jpg",
              "case_status": "pending",
              "region": {
                "id": 1,
                "region": "Greater Accra",
                "author": 1,
                "created_date": "2017-03-29T10:14:22.989213Z",
                "modified": "2017-03-29T10:14:22.989254Z"
              },
              "suburb": {
                "id": 1,
                "region": {
                  "id": 1,
                  "region": "Greater Accra",
                  "author": 1,
                  "created_date": "2017-03-29T10:14:22.989213Z",
                  "modified": "2017-03-29T10:14:22.989254Z"
                },
                "suburb": "Abeka",
                "author": 1,
                "created_date": "2017-03-29T10:14:38.891566Z",
                "modified": "2017-03-29T10:14:38.891606Z"
              },
              "land_mark": "School Junction",
              "author": 13,
              "gravity": false,
              "count_gravity": 0,
              "created_date": "2017-04-19T10:10:47.986632Z"
            },
            {
              "id": 63,
              "case_number": "CB85E9F468",
              "case_category": {
                "id": 2,
                "category_name": "Flood",
                "description": "This is a description about water",
                "category_image": "https://transgovgh-stage.s3.amazonaws.com/images/flood.jpg",
                "author": 1
              },
              "case_name": "trying the land mark field",
              "case_description": "add brief information to it",
              "case_image_one": "https://transgovgh-stage.s3.amazonaws.com/case_image_one_folder/1492082066616t133t90ab8vng5t6ob7lp1d8k7IMG-20170410-WA000-1.jpg",
              "case_image_two": "https://transgovgh-stage.s3.amazonaws.com/case_image_two_folder/14920820666279rud21mi8nf02dd8e1r0feopcmIMG_20170410_19425211-1.jpg",
              "case_image_three": "https://transgovgh-stage.s3.amazonaws.com/case_image_three_folder/14920820666271slrlqbgr84fjsnlup8vj76vekIMG-20170410-WA0003.jpg",
              "case_status": "pending",
              "region": {
                "id": 1,
                "region": "Greater Accra",
                "author": 1,
                "created_date": "2017-03-29T10:14:22.989213Z",
                "modified": "2017-03-29T10:14:22.989254Z"
              },
              "suburb": {
                "id": 1,
                "region": {
                  "id": 1,
                  "region": "Greater Accra",
                  "author": 1,
                  "created_date": "2017-03-29T10:14:22.989213Z",
                  "modified": "2017-03-29T10:14:22.989254Z"
                },
                "suburb": "Abeka",
                "author": 1,
                "created_date": "2017-03-29T10:14:38.891566Z",
                "modified": "2017-03-29T10:14:38.891606Z"
              },
              "land_mark": "close to Nana krom junction besides the filling station",
              "author": 22,
              "gravity": false,
              "count_gravity": 0,
              "created_date": "2017-04-13T11:14:41.845513Z"
            },
            {
              "id": 62,
              "case_number": "CA6154B1AF",
              "case_category": {
                "id": 1,
                "category_name": "Electricity",
                "description": "This is a small description about this category",
                "category_image": "https://transgovgh-stage.s3.amazonaws.com/images/electric.jpg",
                "author": 1
              },
              "case_name": "Enter a name up to 100 words and  i have a lot to write Bubu",
              "case_description": "Descriptiong of trying to another example fault  in postman",
              "case_image_one": "https://transgovgh-stage.s3.amazonaws.com/case_image_one_folder/test.jpg",
              "case_image_two": "https://transgovgh-stage.s3.amazonaws.com/case_image_two_folder/Screenshot_from_2016-01-26_195933.jpg",
              "case_image_three": "https://transgovgh-stage.s3.amazonaws.com/case_image_three_folder/Screenshot_from_2015-09-24_064144.jpg",
              "case_status": "pending",
              "region": {
                "id": 1,
                "region": "Greater Accra",
                "author": 1,
                "created_date": "2017-03-29T10:14:22.989213Z",
                "modified": "2017-03-29T10:14:22.989254Z"
              },
              "suburb": {
                "id": 1,
                "region": {
                  "id": 1,
                  "region": "Greater Accra",
                  "author": 1,
                  "created_date": "2017-03-29T10:14:22.989213Z",
                  "modified": "2017-03-29T10:14:22.989254Z"
                },
                "suburb": "Abeka",
                "author": 1,
                "created_date": "2017-03-29T10:14:38.891566Z",
                "modified": "2017-03-29T10:14:38.891606Z"
              },
              "land_mark": "Close to american house and i have to add more text",
              "author": 1,
              "gravity": false,
              "count_gravity": 0,
              "created_date": "2017-04-13T10:59:14.195470Z"
            },
            {
              "id": 61,
              "case_number": "60554A6A12",
              "case_category": {
                "id": 6,
                "category_name": "Test",
                "description": "",
                "category_image": "https://transgovgh-stage.s3.amazonaws.com/images/category-drains0.jpg",
                "author": 1
              },
              "case_name": "icjjddkfkvcjxjJzclvlgl",
              "case_description": "udidkcvkcjfjdcivkckcckclco",
              "case_image_one": "https://transgovgh-stage.s3.amazonaws.com/case_image_one_folder/1492010027574mql7f3fm0k3mmqe8ifthe77303IMG-20170410-WA0004.jpg",
              "case_image_two": "https://transgovgh-stage.s3.amazonaws.com/case_image_two_folder/14920100275768oe1jj4ci7j5km2ske6crni4guIMG_20170410_194252115.jpg",
              "case_image_three": "https://transgovgh-stage.s3.amazonaws.com/case_image_three_folder/1492010027576vc999lcsat0b2j71hlt2eos2o8IMG-20170410-WA0002.jpg",
              "case_status": "pending",
              "region": {
                "id": 1,
                "region": "Greater Accra",
                "author": 1,
                "created_date": "2017-03-29T10:14:22.989213Z",
                "modified": "2017-03-29T10:14:22.989254Z"
              },
              "suburb": {
                "id": 1,
                "region": {
                  "id": 1,
                  "region": "Greater Accra",
                  "author": 1,
                  "created_date": "2017-03-29T10:14:22.989213Z",
                  "modified": "2017-03-29T10:14:22.989254Z"
                },
                "suburb": "Abeka",
                "author": 1,
                "created_date": "2017-03-29T10:14:38.891566Z",
                "modified": "2017-03-29T10:14:38.891606Z"
              },
              "land_mark": "jxkxj,hzudjfgovovlgco",
              "author": 17,
              "gravity": false,
              "count_gravity": 0,
              "created_date": "2017-04-12T15:14:44.194165Z"
            },
            {
              "id": 60,
              "case_number": "B7D23EC53F",
              "case_category": {
                "id": 1,
                "category_name": "Electricity",
                "description": "This is a small description about this category",
                "category_image": "https://transgovgh-stage.s3.amazonaws.com/images/electric.jpg",
                "author": 1
              },
              "case_name": "Enter a name up to 100 words and  i have a lot to write",
              "case_description": "Descriptiong of trying to another example fault  in postman",
              "case_image_one": "https://transgovgh-stage.s3.amazonaws.com/case_image_one_folder/test.jpg",
              "case_image_two": "https://transgovgh-stage.s3.amazonaws.com/case_image_two_folder/Screenshot_from_2016-01-26_195933.jpg",
              "case_image_three": "https://transgovgh-stage.s3.amazonaws.com/case_image_three_folder/Screenshot_from_2015-09-24_064144.jpg",
              "case_status": "pending",
              "region": {
                "id": 1,
                "region": "Greater Accra",
                "author": 1,
                "created_date": "2017-03-29T10:14:22.989213Z",
                "modified": "2017-03-29T10:14:22.989254Z"
              },
              "suburb": {
                "id": 1,
                "region": {
                  "id": 1,
                  "region": "Greater Accra",
                  "author": 1,
                  "created_date": "2017-03-29T10:14:22.989213Z",
                  "modified": "2017-03-29T10:14:22.989254Z"
                },
                "suburb": "Abeka",
                "author": 1,
                "created_date": "2017-03-29T10:14:38.891566Z",
                "modified": "2017-03-29T10:14:38.891606Z"
              },
              "land_mark": "Close to american house and i have to add more text",
              "author": 1,
              "gravity": false,
              "count_gravity": 0,
              "created_date": "2017-04-12T15:12:35.574406Z"
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
