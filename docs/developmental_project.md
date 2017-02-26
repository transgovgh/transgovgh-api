### Get All projects
- Method: `GET`

- Endpoint: `https://api.example.org/api/v1.0/all-projects/`

 - Response: ``200 ok``

        [
          {
            "id": 1,
            "project_name": "New project for Test",
            "project_description": "Description for project for test",
            "amount_allocated": "0",
            "estimated_budget_GOG": "0",
            "estimated_budget_IGF": "0",
            "estimated_budget_Donor": "0",
            "actual_Budget_Spend": "0",
            "project_contact_person": "Kennedy Anyinatoe",
            "project_contractor": "Kennedy Anyinatoe",
            "project_status": "Ongoing",
            "project_category": "school",
            "start_date": "2017-02-07",
            "end_date": "2017-02-07",
            "completeness": "20",
            "project_location": "Tema",
            "regions": "Greater Accra",
            "sub_metro": "Ablekuma Central Sub Metro",
            "position": "5.9657536710655235,-0.703125",
            "project_image": "http://localhost:8000/media/images/vlcsnap-2015-08-28-20h54m02s198_LTAJcYQ.jpg",
            "projectImages": [
              {
                "id": 3,
                "project": 1,
                "additional_project_images": "http://localhost:8000/media/images/Screenshot_from_2015-10-08_165251_QY8fx5g.jpg"
              },
              {
                "id": 2,
                "project": 1,
                "additional_project_images": "http://localhost:8000/media/images/simple-chord-chart-opt_uhDtnGv.jpg"
              },
              {
                "id": 1,
                "project": 1,
                "additional_project_images": "http://localhost:8000/media/images/vvvvvv_yOEl0Vf.jpg"
              }
            ],
            "count_likes": 0,
            "published_date": null,
            "modified": "2017-02-07T13:52:30.347306Z"
          },
          {
            "id": 2,
            "project_name": "another project",
            "project_description": "another project information",
            "amount_allocated": "6516516556",
            "estimated_budget_GOG": "5161651",
            "estimated_budget_IGF": "0059498",
            "estimated_budget_Donor": "4949816151",
            "actual_Budget_Spend": "984616988",
            "project_contact_person": "Kennedy Anyinatoe",
            "project_contractor": "Kennedy Anyinatoe",
            "project_status": "Ongoing",
            "project_category": "school",
            "start_date": "2017-02-20",
            "end_date": "2017-02-20",
            "completeness": "10",
            "project_location": "Tema",
            "regions": "Ashanti Region",
            "sub_metro": "Ablekuma South Sub Metro",
            "position": "5.9657536710655235,-0.703125",
            "project_image": "http://localhost:8000/media/images/teen-girl_WW4Ud8e.jpg",
            "projectImages": [
              {
                "id": 6,
                "project": 2,
                "additional_project_images": "http://localhost:8000/media/images/simple-chord-chart-opt_YcCsGCL.jpg"
              },
              {
                "id": 5,
                "project": 2,
                "additional_project_images": "http://localhost:8000/media/images/Screenshot_from_2016-03-06_135734.jpg"
              },
              {
                "id": 4,
                "project": 2,
                "additional_project_images": "http://localhost:8000/media/images/vvvvvv_erNxPWM.jpg"
              }
            ],
            "count_likes": 0,
            "published_date": null,
            "modified": "2017-02-20T18:58:58.516633Z"
          },
          
        ]



### Favourite a project
- Method: `POST`

- Endpoint: `https://api.example.org/api/v1.0/all-projects/{pk}/like/`

- User Authorization: ``Required`` 

          "Authorization": "Token xxxxxxxxxxxxx"

 - Response: ``201 Created``

         {
          "likes": 1,
          "success": true
         }


### Get all images for all projects
- Method: `GET`

 - Endpoint: `https://api.example.org/api/v1.0/project-images/`

- User Authorization: ``Required`` 

          "Authorization": "Token xxxxxxxxxxxxx"
 - Response: ``201 Created``

         [
          {
            "id": 1,
            "project": 1,
            "additional_project_images": "http://localhost:8000/media/images/vvvvvv_yOEl0Vf.jpg"
          },
          {
            "id": 2,
            "project": 1,
            "additional_project_images": "http://localhost:8000/media/images/simple-chord-chart-opt_uhDtnGv.jpg"
          },
          {
            "id": 3,
            "project": 1,
            "additional_project_images": "http://localhost:8000/media/images/Screenshot_from_2015-10-08_165251_QY8fx5g.jpg"
          },
          {
            "id": 4,
            "project": 2,
            "additional_project_images": "http://localhost:8000/media/images/vvvvvv_erNxPWM.jpg"
          },
          {
            "id": 5,
            "project": 2,
            "additional_project_images": "http://localhost:8000/media/images/Screenshot_from_2016-03-06_135734.jpg"
          },
          {
            "id": 6,
            "project": 2,
            "additional_project_images": "http://localhost:8000/media/images/simple-chord-chart-opt_YcCsGCL.jpg"
          }
        ]
