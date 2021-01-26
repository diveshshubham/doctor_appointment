HOw to run - 
1. Make tables as per the questions
2. Install depencies - npm install express mysql moment body-parser express-validator --save
3. run index file - noe index.js

Assumptions: 
    -doctor is available in between - 12:01 AM - 11:59 PM
    -table is exist for patient_booking

fututre work :
    -booking database can be implemented
    -24 hrs service can be made
    -validation for date and time can be done
    -can be done using mongo db
    -a separate holiday date can be made when patient cannot book appointment 

Endpoint:http://localhost:8082/doc_avb
Method : Post
Sample Request Body : 
    {
        "doctor_id":"5",
        "start_time":"11:30 AM",
        "end_time": "12:30 PM",
        "no_of_patients": "2"
    }

Response: 
    {
        "message": "sucessfully added"
    }

**refer images with title starts with ans1


///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Endpoint:http://localhost:8082/slot_avbl
Method : Post
Sample Request Body :
    {
        "appointment_date": "22-01-2020",
        "patient_id": "200",
        "doctor_time_slot_id": "1",
        "number_of_patient": "4"
    }

Response: 
 "current": [
        {
            "status": "available for you",
            "time": "09:30 - 10:00"
        },
        {
            "status": "available for you",
            "time": "10:00 - 10:30"
        },
        {
            "status": "available for you",
            "time": "10:30 - 11:00"
        },
        {
            "status": "available for you",
            "time": "11:00 - 11:30"
        }
    ],
    "next": [
        {
            "status": "available for next patient",
            "time": "11:30 - 12:00"
        },
        {
            "status": "available for next patient",
            "time": "12:00 - 12:30"
        }
    ]
}


Sample Request: //here the doctor id exixst in patient_booking_slot
    {
        "appointment_date": "22-01-2020",
        "patient_id": "200",
        "doctor_time_slot_id": "5",
        "number_of_patient": "4"
    }

Response : 
    {
        "message": "sorry!Doctor is not available"
    }

**refer images with title starts with ans2
