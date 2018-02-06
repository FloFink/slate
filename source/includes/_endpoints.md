# Application
## List all applications or specify a query

> output on success

```json
{
    "data": [
        {
            "ratings": [
                {
                    "user": {
                        "email": "string",
                        "firstname": "string",
                        "middlename": "string",
                        "lastname": "string"
                    },
                    "rating": "integer"
                }
            ],
            "id": "integer",
            "candidate_id": "reference",
            "job_id": "reference",
            "is_finished": "boolean",
            "finished_at": "DateTime",
            "created_at": "DateTime",
            "canceled_at": "DateTime",
            "has_upload_task": "boolean",
            "motivational_letter": "string",
            "xrm_tracking_id": "string",
            "current_job_application_status": {
                "id": "integer",
                "name": "string",
                "abbreviation": "string",
                "is_default": "boolean",
                "is_rejected": "boolean",
                "is_hired": "boolean",
                "is_rejected_by_candidate": "boolean"
            },
            "job_application_status_logs": [
                {
                    "created_at": "DateTime",
                    "job_application_status": "object (JobApplicationStatus)",
                    "user": {
                        "email": "string",
                        "firstname": "string",
                        "middlename": "string",
                        "lastname": "string"
                    },
                    "reason": "string",
                    "start_reminder_at": "DateTime"
                }
            ],
            "recruiter_files": [
                {
                    "filename": "string",
                    "base64_content": "string",
                    "is_visible_for_candidate": "boolean",
                    "source": "string"
                }
            ]
        }
    ],
    "links": {
        "self": "string",
        "first": "string",
        "prev": "string",
        "next": "string",
        "last": "string"
    }
}
```

`GET /v1/application`
### Query parameters
Parameter | Type | Remarks
--------- | -----| -------
id|integer|
candidate_id|reference|
job_id|reference|
is_finished|boolean|
finished_at|DateTime|
created_at|DateTime|
canceled_at|DateTime|
has_upload_task|boolean|
motivational_letter|string|
xrm_tracking_id|string|
current_job_application_status[id]|integer|
current_job_application_status[name]|string|
current_job_application_status[abbreviation]|string|
current_job_application_status[is_default]|boolean|
current_job_application_status[is_rejected]|boolean|
current_job_application_status[is_hired]|boolean|
current_job_application_status[is_rejected_by_candidate]|boolean|
job_application_status_logs[created_at]|DateTime|
job_application_status_logs[job_application_status]|object (JobApplicationStatus)|
job_application_status_logs[user][email]|string|
job_application_status_logs[user][firstname]|string|
job_application_status_logs[user][middlename]|string|
job_application_status_logs[user][lastname]|string|
job_application_status_logs[reason]|string|
job_application_status_logs[start_reminder_at]|DateTime|
recruiter_files[filename]|string|
recruiter_files[is_visible_for_candidate]|boolean|
recruiter_files[source]|string|
### Response codes
Response Code | Description
----------- | -----------
`200`|Returned on success
## Add a new application

> expected input

```json
{
    "candidate_id": "reference",
    "job_id": "reference",
    "is_finished": "boolean",
    "referer": "string",
    "xrm_tracking_id": "string",
    "recruiter_files": [
        {
            "filename": "string",
            "base64_content": "string",
            "is_visible_for_candidate": "boolean",
            "source": "string"
        }
    ],
    "motivational_letter": "string"
}
```

> output on success

```json
{
    "ratings": [
        {
            "user": {
                "email": "string",
                "firstname": "string",
                "middlename": "string",
                "lastname": "string"
            },
            "rating": "integer"
        }
    ],
    "id": "integer",
    "candidate_id": "reference",
    "job_id": "reference",
    "is_finished": "boolean",
    "finished_at": "DateTime",
    "created_at": "DateTime",
    "canceled_at": "DateTime",
    "has_upload_task": "boolean",
    "motivational_letter": "string",
    "xrm_tracking_id": "string",
    "current_job_application_status": {
        "id": "integer",
        "name": "string",
        "abbreviation": "string",
        "is_default": "boolean",
        "is_rejected": "boolean",
        "is_hired": "boolean",
        "is_rejected_by_candidate": "boolean"
    },
    "job_application_status_logs": [
        {
            "created_at": "DateTime",
            "job_application_status": "object (JobApplicationStatus)",
            "user": {
                "email": "string",
                "firstname": "string",
                "middlename": "string",
                "lastname": "string"
            },
            "reason": "string",
            "start_reminder_at": "DateTime"
        }
    ],
    "recruiter_files": [
        {
            "filename": "string",
            "base64_content": "string",
            "is_visible_for_candidate": "boolean",
            "source": "string"
        }
    ]
}
```

`POST /v1/application`
### Response codes
Response Code | Description
----------- | -----------
`201`|Returned on success
## Find one application by its ID

> output on success

```json
{
    "ratings": [
        {
            "user": {
                "email": "string",
                "firstname": "string",
                "middlename": "string",
                "lastname": "string"
            },
            "rating": "integer"
        }
    ],
    "id": "integer",
    "candidate_id": "reference",
    "job_id": "reference",
    "is_finished": "boolean",
    "finished_at": "DateTime",
    "created_at": "DateTime",
    "canceled_at": "DateTime",
    "has_upload_task": "boolean",
    "motivational_letter": "string",
    "xrm_tracking_id": "string",
    "current_job_application_status": {
        "id": "integer",
        "name": "string",
        "abbreviation": "string",
        "is_default": "boolean",
        "is_rejected": "boolean",
        "is_hired": "boolean",
        "is_rejected_by_candidate": "boolean"
    },
    "job_application_status_logs": [
        {
            "created_at": "DateTime",
            "job_application_status": "object (JobApplicationStatus)",
            "user": {
                "email": "string",
                "firstname": "string",
                "middlename": "string",
                "lastname": "string"
            },
            "reason": "string",
            "start_reminder_at": "DateTime"
        }
    ],
    "recruiter_files": [
        {
            "filename": "string",
            "base64_content": "string",
            "is_visible_for_candidate": "boolean",
            "source": "string"
        }
    ]
}
```

`GET /v1/application/{id}`
### Response codes
Response Code | Description
----------- | -----------
`200`|Returned on success
## Partially or fully update an existing application

> expected input

```json
{
    "is_finished": "boolean",
    "referer": "string",
    "xrm_tracking_id": "string",
    "recruiter_files": [
        {
            "filename": "string",
            "base64_content": "string",
            "is_visible_for_candidate": "boolean",
            "source": "string"
        }
    ]
}
```

> output on success

```json
{
    "ratings": [
        {
            "user": {
                "email": "string",
                "firstname": "string",
                "middlename": "string",
                "lastname": "string"
            },
            "rating": "integer"
        }
    ],
    "id": "integer",
    "candidate_id": "reference",
    "job_id": "reference",
    "is_finished": "boolean",
    "finished_at": "DateTime",
    "created_at": "DateTime",
    "canceled_at": "DateTime",
    "has_upload_task": "boolean",
    "motivational_letter": "string",
    "xrm_tracking_id": "string",
    "current_job_application_status": {
        "id": "integer",
        "name": "string",
        "abbreviation": "string",
        "is_default": "boolean",
        "is_rejected": "boolean",
        "is_hired": "boolean",
        "is_rejected_by_candidate": "boolean"
    },
    "job_application_status_logs": [
        {
            "created_at": "DateTime",
            "job_application_status": "object (JobApplicationStatus)",
            "user": {
                "email": "string",
                "firstname": "string",
                "middlename": "string",
                "lastname": "string"
            },
            "reason": "string",
            "start_reminder_at": "DateTime"
        }
    ],
    "recruiter_files": [
        {
            "filename": "string",
            "base64_content": "string",
            "is_visible_for_candidate": "boolean",
            "source": "string"
        }
    ]
}
```

`PATCH /v1/application/{id}`
### Response codes
Response Code | Description
----------- | -----------
`200`|Returned on success
## Set the status of an application

> expected input

```json
{
    "reason": "string"
}
```

`PUT /v1/application/{id}/status/{status_id}`
### Response codes
Response Code | Description
----------- | -----------
`204`|Returned on success
# Candidate
## List all candidates or specify a query

> output on success

```json
{
    "data": [
        {
            "id": "integer",
            "profile": {
                "firstname": "string",
                "middlename": "string",
                "lastname": "string",
                "phone": "string",
                "avatar": {
                    "filename": "string",
                    "base64_content": "string",
                    "file_type": "string"
                },
                "birthday": "DateTime",
                "gender": "string",
                "city_id": "reference",
                "homeaddress": "string",
                "street": "string",
                "zip_code": "string",
                "city_name": "string",
                "country_of_residence": "string",
                "nationality": "string",
                "awards": "string",
                "organizations": "string",
                "workaddress": "string",
                "positions": [
                    {
                        "title": "string",
                        "department_id": "reference",
                        "description": "string",
                        "company_name": "string",
                        "industry_id": "reference",
                        "position_type": "reference",
                        "seniority": "reference",
                        "start_date": "DateTime",
                        "end_date": "DateTime",
                        "city": "string"
                    }
                ],
                "educations": [
                    {
                        "school": "string",
                        "subject": "string",
                        "specialized_subjects": "string",
                        "degree": "string",
                        "start_date": "DateTime",
                        "end_date": "DateTime"
                    }
                ],
                "current_position": "object (Position)",
                "current_education": "object (Education)",
                "interests": [
                    "array of objects (string)"
                ],
                "skill_aliases": [
                    "array of objects (string)"
                ],
                "additional_emails": [
                    {
                        "type": "reference",
                        "address": "string"
                    }
                ],
                "ims": [
                    {
                        "type": "string",
                        "address": "string"
                    }
                ],
                "additional_phones": [
                    {
                        "type": "reference",
                        "number": "string"
                    }
                ],
                "urls": [
                    {
                        "type": "string",
                        "address": "string"
                    }
                ],
                "languages": [
                    {
                        "code": "reference",
                        "level": "reference"
                    }
                ],
                "advanced_trainings": [
                    {
                        "name": "string",
                        "year": "integer"
                    }
                ]
            },
            "email": "string",
            "created_at": "DateTime",
            "updated_at": "DateTime",
            "last_login": "DateTime",
            "last_activity_at": "DateTime",
            "language": "string",
            "is_confirmed": "boolean",
            "is_internal": "boolean",
            "created_by": [],
            "custom_fields": [
                {
                    "custom_field_id": "reference",
                    "values": [
                        {
                            "id": "integer",
                            "value": "string"
                        }
                    ]
                }
            ],
            "candidate_tag_ids": [
                "array of objects (reference)"
            ],
            "job_applications": [
                {
                    "id": "integer",
                    "job_id": "reference"
                }
            ],
            "has_cv_upload": "boolean",
            "cv_file": {
                "filename": "string",
                "base64_content": "string",
                "file_type": "string"
            },
            "facebook_id": "string",
            "xing_id": "string",
            "linkedin_id": "string",
            "reference_id": "integer"
        }
    ],
    "links": {
        "self": "string",
        "first": "string",
        "prev": "string",
        "next": "string",
        "last": "string"
    }
}
```

`GET /v1/candidate`
### Query parameters
Parameter | Type | Remarks
--------- | -----| -------
profile[firstname]|string|
profile[middlename]|string|
profile[lastname]|string|
profile[phone]|string|
profile[birthday]|DateTime|
profile[gender]|string|
profile[city_id]|reference|
profile[homeaddress]|string|
profile[street]|string|
profile[zip_code]|string|
profile[city_name]|string|
profile[country_of_residence]|string|ISO 3166-1 alpha-2 country code
profile[nationality]|string|ISO 3166-1 alpha-2 country code
profile[awards]|string|
profile[organizations]|string|
profile[workaddress]|string|
profile[positions][title]|string|
profile[positions][department_id]|reference|
profile[positions][description]|string|
profile[positions][company_name]|string|
profile[positions][industry_id]|reference|
profile[positions][position_type]|reference|'full-time', 'part-time', 'internship', 'freelancer', etc ...
profile[positions][seniority]|reference|'Entry Level', 'Professional/Experienced', 'Student/Intern', 'Manager', etc ...
profile[positions][start_date]|DateTime|
profile[positions][end_date]|DateTime|
profile[positions][city]|string|
profile[educations][school]|string|
profile[educations][subject]|string|
profile[educations][specialized_subjects]|string|
profile[educations][degree]|string|
profile[educations][start_date]|DateTime|
profile[educations][end_date]|DateTime|
profile[current_position]|object (Position)|
profile[current_education]|object (Education)|
profile[interests]|array of objects (string)|
profile[skill_aliases]|array of objects (string)|
profile[additional_emails][type]|reference|'private' or 'work'
profile[additional_emails][address]|string|
profile[ims][type]|string|
profile[ims][address]|string|
profile[additional_phones][type]|reference|'mobile', 'work', 'home', or 'fax'
profile[additional_phones][number]|string|
profile[urls][type]|string|
profile[urls][address]|string|
profile[languages][code]|reference|ISO 639-1 language code
profile[languages][level]|reference|'native', 'fluent', 'good', 'intermediate', 'basic', or 'beginner'
profile[advanced_trainings][name]|string|
profile[advanced_trainings][year]|integer|
email|string|
id|integer|
created_at|DateTime|
updated_at|DateTime|
last_login|DateTime|
last_activity_at|DateTime|
language|string|ISO 639-1 language code
is_confirmed|boolean|
is_internal|boolean|
custom_fields[custom_field_id]|reference|
custom_fields[values][id]|integer|
custom_fields[values][value]|string|
candidate_tag_ids|array of objects (reference)|
facebook_id|string|
xing_id|string|
linkedin_id|string|
reference_id|integer|
### Response codes
Response Code | Description
----------- | -----------
`200`|Returned on success
## Add a new candidate

> expected input

```json
{
    "profile": {
        "firstname": "string",
        "middlename": "string",
        "lastname": "string",
        "phone": "string",
        "avatar": {
            "base64_content": "string",
            "file_type": "string"
        },
        "birthday": "DateTime",
        "gender": "string",
        "city_id": "reference",
        "homeaddress": "string",
        "street": "string",
        "zip_code": "string",
        "city_name": "string",
        "country_of_residence": "string",
        "nationality": "string",
        "awards": "string",
        "organizations": "string",
        "workaddress": "string",
        "positions": [
            {
                "title": "string",
                "department_id": "reference",
                "description": "string",
                "company_name": "string",
                "industry_id": "reference",
                "position_type": "reference",
                "seniority": "reference",
                "start_date": "DateTime",
                "end_date": "DateTime",
                "city": "string"
            }
        ],
        "educations": [
            {
                "school": "string",
                "subject": "string",
                "specialized_subjects": "string",
                "degree": "string",
                "start_date": "DateTime",
                "end_date": "DateTime"
            }
        ],
        "interests": [
            "array of objects (string)"
        ],
        "skill_aliases": [
            "array of objects (string)"
        ],
        "additional_emails": [
            {
                "type": "reference",
                "address": "string"
            }
        ],
        "ims": [
            {
                "type": "string",
                "address": "string"
            }
        ],
        "additional_phones": [
            {
                "type": "reference",
                "number": "string"
            }
        ],
        "urls": [
            {
                "type": "string",
                "address": "string"
            }
        ],
        "languages": [
            {
                "code": "reference",
                "level": "reference"
            }
        ],
        "advanced_trainings": [
            {
                "name": "string",
                "year": "integer"
            }
        ]
    },
    "email": "string",
    "language": "string",
    "is_internal": "boolean",
    "custom_fields": [
        {
            "custom_field_id": "reference",
            "values": [
                {
                    "id": "integer",
                    "value": "string"
                }
            ]
        }
    ],
    "candidate_tag_ids": [
        "array of objects (reference)"
    ],
    "cv_file": {
        "base64_content": "string",
        "file_type": "string"
    },
    "facebook_id": "string",
    "xing_id": "string",
    "linkedin_id": "string",
    "job_id": "integer",
    "send_email": "boolean"
}
```

> output on success

```json
{
    "profile": {
        "firstname": "string",
        "middlename": "string",
        "lastname": "string",
        "phone": "string",
        "avatar": {
            "filename": "string",
            "base64_content": "string",
            "file_type": "string"
        },
        "birthday": "DateTime",
        "gender": "string",
        "city_id": "reference",
        "homeaddress": "string",
        "street": "string",
        "zip_code": "string",
        "city_name": "string",
        "country_of_residence": "string",
        "nationality": "string",
        "awards": "string",
        "organizations": "string",
        "workaddress": "string",
        "positions": [
            {
                "title": "string",
                "department_id": "reference",
                "description": "string",
                "company_name": "string",
                "industry_id": "reference",
                "position_type": "reference",
                "seniority": "reference",
                "start_date": "DateTime",
                "end_date": "DateTime",
                "city": "string"
            }
        ],
        "educations": [
            {
                "school": "string",
                "subject": "string",
                "specialized_subjects": "string",
                "degree": "string",
                "start_date": "DateTime",
                "end_date": "DateTime"
            }
        ],
        "current_position": "object (Position)",
        "current_education": "object (Education)",
        "interests": [
            "array of objects (string)"
        ],
        "skill_aliases": [
            "array of objects (string)"
        ],
        "additional_emails": [
            {
                "type": "reference",
                "address": "string"
            }
        ],
        "ims": [
            {
                "type": "string",
                "address": "string"
            }
        ],
        "additional_phones": [
            {
                "type": "reference",
                "number": "string"
            }
        ],
        "urls": [
            {
                "type": "string",
                "address": "string"
            }
        ],
        "languages": [
            {
                "code": "reference",
                "level": "reference"
            }
        ],
        "advanced_trainings": [
            {
                "name": "string",
                "year": "integer"
            }
        ]
    },
    "email": "string",
    "id": "integer",
    "created_at": "DateTime",
    "updated_at": "DateTime",
    "last_login": "DateTime",
    "last_activity_at": "DateTime",
    "language": "string",
    "is_confirmed": "boolean",
    "is_internal": "boolean",
    "created_by": [],
    "custom_fields": [
        {
            "custom_field_id": "reference",
            "values": [
                {
                    "id": "integer",
                    "value": "string"
                }
            ]
        }
    ],
    "candidate_tag_ids": [
        "array of objects (reference)"
    ],
    "job_applications": [
        {
            "id": "integer",
            "job_id": "reference"
        }
    ],
    "has_cv_upload": "boolean",
    "cv_file": {
        "filename": "string",
        "base64_content": "string",
        "file_type": "string"
    },
    "facebook_id": "string",
    "xing_id": "string",
    "linkedin_id": "string",
    "reference_id": "integer"
}
```

`POST /v1/candidate`
### Response codes
Response Code | Description
----------- | -----------
`201`|Returned on success
## Find one candidate by its ID

> output on success

```json
{
    "profile": {
        "firstname": "string",
        "middlename": "string",
        "lastname": "string",
        "phone": "string",
        "avatar": {
            "filename": "string",
            "base64_content": "string",
            "file_type": "string"
        },
        "birthday": "DateTime",
        "gender": "string",
        "city_id": "reference",
        "homeaddress": "string",
        "street": "string",
        "zip_code": "string",
        "city_name": "string",
        "country_of_residence": "string",
        "nationality": "string",
        "awards": "string",
        "organizations": "string",
        "workaddress": "string",
        "positions": [
            {
                "title": "string",
                "department_id": "reference",
                "description": "string",
                "company_name": "string",
                "industry_id": "reference",
                "position_type": "reference",
                "seniority": "reference",
                "start_date": "DateTime",
                "end_date": "DateTime",
                "city": "string"
            }
        ],
        "educations": [
            {
                "school": "string",
                "subject": "string",
                "specialized_subjects": "string",
                "degree": "string",
                "start_date": "DateTime",
                "end_date": "DateTime"
            }
        ],
        "current_position": "object (Position)",
        "current_education": "object (Education)",
        "interests": [
            "array of objects (string)"
        ],
        "skill_aliases": [
            "array of objects (string)"
        ],
        "additional_emails": [
            {
                "type": "reference",
                "address": "string"
            }
        ],
        "ims": [
            {
                "type": "string",
                "address": "string"
            }
        ],
        "additional_phones": [
            {
                "type": "reference",
                "number": "string"
            }
        ],
        "urls": [
            {
                "type": "string",
                "address": "string"
            }
        ],
        "languages": [
            {
                "code": "reference",
                "level": "reference"
            }
        ],
        "advanced_trainings": [
            {
                "name": "string",
                "year": "integer"
            }
        ]
    },
    "email": "string",
    "id": "integer",
    "created_at": "DateTime",
    "updated_at": "DateTime",
    "last_login": "DateTime",
    "last_activity_at": "DateTime",
    "language": "string",
    "is_confirmed": "boolean",
    "is_internal": "boolean",
    "created_by": [],
    "custom_fields": [
        {
            "custom_field_id": "reference",
            "values": [
                {
                    "id": "integer",
                    "value": "string"
                }
            ]
        }
    ],
    "candidate_tag_ids": [
        "array of objects (reference)"
    ],
    "job_applications": [
        {
            "id": "integer",
            "job_id": "reference"
        }
    ],
    "has_cv_upload": "boolean",
    "cv_file": {
        "filename": "string",
        "base64_content": "string",
        "file_type": "string"
    },
    "facebook_id": "string",
    "xing_id": "string",
    "linkedin_id": "string",
    "reference_id": "integer"
}
```

`GET /v1/candidate/{id}`
### Response codes
Response Code | Description
----------- | -----------
`200`|Returned on success
## Partially or fully update an existing candidate

> expected input

```json
{
    "profile": {
        "firstname": "string",
        "middlename": "string",
        "lastname": "string",
        "phone": "string",
        "avatar": {
            "base64_content": "string",
            "file_type": "string"
        },
        "birthday": "DateTime",
        "gender": "string",
        "city_id": "reference",
        "homeaddress": "string",
        "street": "string",
        "zip_code": "string",
        "city_name": "string",
        "country_of_residence": "string",
        "nationality": "string",
        "awards": "string",
        "organizations": "string",
        "workaddress": "string",
        "positions": [
            {
                "title": "string",
                "department_id": "reference",
                "description": "string",
                "company_name": "string",
                "industry_id": "reference",
                "position_type": "reference",
                "seniority": "reference",
                "start_date": "DateTime",
                "end_date": "DateTime",
                "city": "string"
            }
        ],
        "educations": [
            {
                "school": "string",
                "subject": "string",
                "specialized_subjects": "string",
                "degree": "string",
                "start_date": "DateTime",
                "end_date": "DateTime"
            }
        ],
        "interests": [
            "array of objects (string)"
        ],
        "skill_aliases": [
            "array of objects (string)"
        ],
        "additional_emails": [
            {
                "type": "reference",
                "address": "string"
            }
        ],
        "ims": [
            {
                "type": "string",
                "address": "string"
            }
        ],
        "additional_phones": [
            {
                "type": "reference",
                "number": "string"
            }
        ],
        "urls": [
            {
                "type": "string",
                "address": "string"
            }
        ],
        "languages": [
            {
                "code": "reference",
                "level": "reference"
            }
        ],
        "advanced_trainings": [
            {
                "name": "string",
                "year": "integer"
            }
        ]
    },
    "email": "string",
    "language": "string",
    "is_internal": "boolean",
    "custom_fields": [
        {
            "custom_field_id": "reference",
            "values": [
                {
                    "id": "integer",
                    "value": "string"
                }
            ]
        }
    ],
    "candidate_tag_ids": [
        "array of objects (reference)"
    ],
    "cv_file": {
        "base64_content": "string",
        "file_type": "string"
    },
    "facebook_id": "string",
    "xing_id": "string",
    "linkedin_id": "string"
}
```

> output on success

```json
{
    "profile": {
        "firstname": "string",
        "middlename": "string",
        "lastname": "string",
        "phone": "string",
        "avatar": {
            "filename": "string",
            "base64_content": "string",
            "file_type": "string"
        },
        "birthday": "DateTime",
        "gender": "string",
        "city_id": "reference",
        "homeaddress": "string",
        "street": "string",
        "zip_code": "string",
        "city_name": "string",
        "country_of_residence": "string",
        "nationality": "string",
        "awards": "string",
        "organizations": "string",
        "workaddress": "string",
        "positions": [
            {
                "title": "string",
                "department_id": "reference",
                "description": "string",
                "company_name": "string",
                "industry_id": "reference",
                "position_type": "reference",
                "seniority": "reference",
                "start_date": "DateTime",
                "end_date": "DateTime",
                "city": "string"
            }
        ],
        "educations": [
            {
                "school": "string",
                "subject": "string",
                "specialized_subjects": "string",
                "degree": "string",
                "start_date": "DateTime",
                "end_date": "DateTime"
            }
        ],
        "current_position": "object (Position)",
        "current_education": "object (Education)",
        "interests": [
            "array of objects (string)"
        ],
        "skill_aliases": [
            "array of objects (string)"
        ],
        "additional_emails": [
            {
                "type": "reference",
                "address": "string"
            }
        ],
        "ims": [
            {
                "type": "string",
                "address": "string"
            }
        ],
        "additional_phones": [
            {
                "type": "reference",
                "number": "string"
            }
        ],
        "urls": [
            {
                "type": "string",
                "address": "string"
            }
        ],
        "languages": [
            {
                "code": "reference",
                "level": "reference"
            }
        ],
        "advanced_trainings": [
            {
                "name": "string",
                "year": "integer"
            }
        ]
    },
    "email": "string",
    "id": "integer",
    "created_at": "DateTime",
    "updated_at": "DateTime",
    "last_login": "DateTime",
    "last_activity_at": "DateTime",
    "language": "string",
    "is_confirmed": "boolean",
    "is_internal": "boolean",
    "created_by": [],
    "custom_fields": [
        {
            "custom_field_id": "reference",
            "values": [
                {
                    "id": "integer",
                    "value": "string"
                }
            ]
        }
    ],
    "candidate_tag_ids": [
        "array of objects (reference)"
    ],
    "job_applications": [
        {
            "id": "integer",
            "job_id": "reference"
        }
    ],
    "has_cv_upload": "boolean",
    "cv_file": {
        "filename": "string",
        "base64_content": "string",
        "file_type": "string"
    },
    "facebook_id": "string",
    "xing_id": "string",
    "linkedin_id": "string",
    "reference_id": "integer"
}
```

`PATCH /v1/candidate/{id}`
### Response codes
Response Code | Description
----------- | -----------
`200`|Returned on success
# Other
## List all available candidate tags or specify a query

> output on success

```json
{
    "data": [
        {
            "id": "integer",
            "created_at": "DateTime",
            "name": "string",
            "color_code": "string"
        }
    ],
    "links": {
        "self": "string",
        "first": "string",
        "prev": "string",
        "next": "string",
        "last": "string"
    }
}
```

`GET /v1/candidate_tag`
### Query parameters
Parameter | Type | Remarks
--------- | -----| -------
id|integer|
created_at|DateTime|
name|string|
color_code|string|
### Response codes
Response Code | Description
----------- | -----------
`200`|Returned on success
## Find one candidate tag by its ID

> output on success

```json
{
    "id": "integer",
    "created_at": "DateTime",
    "name": "string",
    "color_code": "string"
}
```

`GET /v1/candidate_tag/{id}`
### Response codes
Response Code | Description
----------- | -----------
`200`|Returned on success
## List all available cities or specify a query

> output on success

```json
{
    "data": [
        {
            "id": "integer",
            "osm_id": "integer",
            "cc": "string",
            "lat": "float",
            "lon": "float",
            "google_id": "string",
            "translations": [
                {
                    "name": "string",
                    "country": "string"
                }
            ]
        }
    ],
    "links": {
        "self": "string",
        "first": "string",
        "prev": "string",
        "next": "string",
        "last": "string"
    }
}
```

`GET /v1/city`
### Query parameters
Parameter | Type | Remarks
--------- | -----| -------
id|integer|
osm_id|integer|
cc|string|
lat|float|
lon|float|
google_id|string|
translations[name]|string|
translations[country]|string|
### Response codes
Response Code | Description
----------- | -----------
`200`|Returned on success
## Find one city by its ID

> output on success

```json
{
    "id": "integer",
    "osm_id": "integer",
    "cc": "string",
    "lat": "float",
    "lon": "float",
    "google_id": "string",
    "translations": [
        {
            "name": "string",
            "country": "string"
        }
    ]
}
```

`GET /v1/city/{id}`
### Response codes
Response Code | Description
----------- | -----------
`200`|Returned on success
## List all available custom fields or specify a query

> output on success

```json
{
    "data": [
        {
            "id": "integer",
            "name": "string",
            "label": "string",
            "possible_values": [
                {
                    "id": "integer",
                    "value": "string"
                }
            ],
            "is_job": "boolean",
            "is_candidate": "boolean"
        }
    ],
    "links": {
        "self": "string",
        "first": "string",
        "prev": "string",
        "next": "string",
        "last": "string"
    }
}
```

`GET /v1/custom_field`
### Query parameters
Parameter | Type | Remarks
--------- | -----| -------
id|integer|
name|string|
label|string|
possible_values[id]|integer|
possible_values[value]|string|
is_job|boolean|
is_candidate|boolean|
### Response codes
Response Code | Description
----------- | -----------
`200`|Returned on success
## Find one custom field by its ID

> output on success

```json
{
    "id": "integer",
    "name": "string",
    "label": "string",
    "possible_values": [
        {
            "id": "integer",
            "value": "string"
        }
    ],
    "is_job": "boolean",
    "is_candidate": "boolean"
}
```

`GET /v1/custom_field/{id}`
### Response codes
Response Code | Description
----------- | -----------
`200`|Returned on success
## List all available departments or specify a query

> output on success

```json
{
    "data": [
        {
            "id": "integer",
            "translations": [
                {
                    "name": "string"
                }
            ]
        }
    ],
    "links": {
        "self": "string",
        "first": "string",
        "prev": "string",
        "next": "string",
        "last": "string"
    }
}
```

`GET /v1/department`
### Query parameters
Parameter | Type | Remarks
--------- | -----| -------
id|integer|
translations[name]|string|
### Response codes
Response Code | Description
----------- | -----------
`200`|Returned on success
## Find one department by its ID

> output on success

```json
{
    "id": "integer",
    "translations": [
        {
            "name": "string"
        }
    ]
}
```

`GET /v1/department/{id}`
### Response codes
Response Code | Description
----------- | -----------
`200`|Returned on success
## List all available industries or specify a query

> output on success

```json
{
    "data": [
        {
            "id": "integer",
            "translations": [
                {
                    "name": "string"
                }
            ]
        }
    ],
    "links": {
        "self": "string",
        "first": "string",
        "prev": "string",
        "next": "string",
        "last": "string"
    }
}
```

`GET /v1/industry`
### Query parameters
Parameter | Type | Remarks
--------- | -----| -------
id|integer|
translations[name]|string|
### Response codes
Response Code | Description
----------- | -----------
`200`|Returned on success
## Find one industry by its ID

> output on success

```json
{
    "id": "integer",
    "translations": [
        {
            "name": "string"
        }
    ]
}
```

`GET /v1/industry/{id}`
### Response codes
Response Code | Description
----------- | -----------
`200`|Returned on success
## List all available status sets or specify a query

> output on success

```json
{
    "data": [
        {
            "id": "integer",
            "statuses": [
                {
                    "id": "integer",
                    "name": "string",
                    "abbreviation": "string",
                    "is_default": "boolean",
                    "is_rejected": "boolean",
                    "is_hired": "boolean",
                    "is_rejected_by_candidate": "boolean"
                }
            ],
            "job_ids": [
                "array of objects (reference)"
            ]
        }
    ],
    "links": {
        "self": "string",
        "first": "string",
        "prev": "string",
        "next": "string",
        "last": "string"
    }
}
```

`GET /v1/status_set`
### Query parameters
Parameter | Type | Remarks
--------- | -----| -------
id|integer|
statuses[id]|integer|
statuses[name]|string|
statuses[abbreviation]|string|
statuses[is_default]|boolean|
statuses[is_rejected]|boolean|
statuses[is_hired]|boolean|
statuses[is_rejected_by_candidate]|boolean|
job_ids|array of objects (reference)|
### Response codes
Response Code | Description
----------- | -----------
`200`|Returned on success
## Find one status set by its ID

> output on success

```json
{
    "id": "integer",
    "statuses": [
        {
            "id": "integer",
            "name": "string",
            "abbreviation": "string",
            "is_default": "boolean",
            "is_rejected": "boolean",
            "is_hired": "boolean",
            "is_rejected_by_candidate": "boolean"
        }
    ],
    "job_ids": [
        "array of objects (reference)"
    ]
}
```

`GET /v1/status_set/{id}`
### Response codes
Response Code | Description
----------- | -----------
`200`|Returned on success
# Job
## List all jobs or specify a query

> output on success

```json
{
    "data": [
        {
            "id": "integer",
            "handle": "string",
            "short_handle": "string",
            "user": {
                "email": "string",
                "firstname": "string",
                "middlename": "string",
                "lastname": "string"
            },
            "title": "string",
            "created_at": "DateTime",
            "department_id": "reference",
            "job_template": {
                "created_at": "DateTime",
                "name": "string",
                "html": "string"
            },
            "description": "string",
            "salary": "float",
            "position_type": "reference",
            "city_id": "reference",
            "seniority": "reference",
            "industry_id": "reference",
            "is_published_on_widget": "boolean",
            "is_published_on_job_center": "boolean",
            "published_at": "DateTime",
            "requested_publication_at": "DateTime",
            "custom_fields": [
                {
                    "custom_field_id": "reference",
                    "values": [
                        {
                            "id": "integer",
                            "value": "string"
                        }
                    ]
                }
            ],
            "finished_at": "DateTime",
            "start_of_work": "DateTime",
            "head_count": "integer",
            "apply_url": "string",
            "job_contents": [
                {
                    "created_at": "DateTime",
                    "content": "string"
                }
            ],
            "main_contact": "object (User)",
            "job_application_status_set": {
                "id": "integer",
                "statuses": [
                    {
                        "id": "integer",
                        "name": "string",
                        "abbreviation": "string",
                        "is_default": "boolean",
                        "is_rejected": "boolean",
                        "is_hired": "boolean",
                        "is_rejected_by_candidate": "boolean"
                    }
                ]
            }
        }
    ],
    "links": {
        "self": "string",
        "first": "string",
        "prev": "string",
        "next": "string",
        "last": "string"
    }
}
```

`GET /v1/job`
### Query parameters
Parameter | Type | Remarks
--------- | -----| -------
id|integer|
handle|string|
short_handle|string|
user[email]|string|
user[firstname]|string|
user[middlename]|string|
user[lastname]|string|
title|string|
created_at|DateTime|
department_id|reference|
job_template[created_at]|DateTime|
job_template[name]|string|
job_template[html]|string|
description|string|
salary|float|
position_type|reference|'full-time', 'part-time', 'internship', 'freelancer', etc ...
city_id|reference|
seniority|reference|'Entry Level', 'Professional/Experienced', 'Student/Intern', 'Manager', etc ...
industry_id|reference|
is_published_on_widget|boolean|
is_published_on_job_center|boolean|
published_at|DateTime|
requested_publication_at|DateTime|
custom_fields[custom_field_id]|reference|
custom_fields[values][id]|integer|
custom_fields[values][value]|string|
finished_at|DateTime|
start_of_work|DateTime|
head_count|integer|
apply_url|string|
job_contents[created_at]|DateTime|
job_contents[content]|string|
job_application_status_set[id]|integer|
job_application_status_set[statuses][id]|integer|
job_application_status_set[statuses][name]|string|
job_application_status_set[statuses][abbreviation]|string|
job_application_status_set[statuses][is_default]|boolean|
job_application_status_set[statuses][is_rejected]|boolean|
job_application_status_set[statuses][is_hired]|boolean|
job_application_status_set[statuses][is_rejected_by_candidate]|boolean|
### Response codes
Response Code | Description
----------- | -----------
`200`|Returned on success
## Find one job by its ID

> output on success

```json
{
    "id": "integer",
    "handle": "string",
    "short_handle": "string",
    "user": {
        "email": "string",
        "firstname": "string",
        "middlename": "string",
        "lastname": "string"
    },
    "title": "string",
    "created_at": "DateTime",
    "department_id": "reference",
    "job_template": {
        "created_at": "DateTime",
        "name": "string",
        "html": "string"
    },
    "description": "string",
    "salary": "float",
    "position_type": "reference",
    "city_id": "reference",
    "seniority": "reference",
    "industry_id": "reference",
    "is_published_on_widget": "boolean",
    "is_published_on_job_center": "boolean",
    "published_at": "DateTime",
    "requested_publication_at": "DateTime",
    "custom_fields": [
        {
            "custom_field_id": "reference",
            "values": [
                {
                    "id": "integer",
                    "value": "string"
                }
            ]
        }
    ],
    "finished_at": "DateTime",
    "start_of_work": "DateTime",
    "head_count": "integer",
    "apply_url": "string",
    "job_contents": [
        {
            "created_at": "DateTime",
            "content": "string"
        }
    ],
    "main_contact": "object (User)",
    "job_application_status_set": {
        "id": "integer",
        "statuses": [
            {
                "id": "integer",
                "name": "string",
                "abbreviation": "string",
                "is_default": "boolean",
                "is_rejected": "boolean",
                "is_hired": "boolean",
                "is_rejected_by_candidate": "boolean"
            }
        ]
    }
}
```

`GET /v1/job/{id}`
### Response codes
Response Code | Description
----------- | -----------
`200`|Returned on success
## Partially or fully update an existing job

> expected input

```json
{
    "title": "string",
    "department_id": "reference",
    "description": "string",
    "salary": "float",
    "position_type": "reference",
    "city_id": "reference",
    "seniority": "reference",
    "industry_id": "reference",
    "custom_fields": [
        {
            "custom_field_id": "reference",
            "values": [
                {
                    "id": "integer",
                    "value": "string"
                }
            ]
        }
    ],
    "start_of_work": "DateTime",
    "head_count": "integer"
}
```

> output on success

```json
{
    "id": "integer",
    "handle": "string",
    "short_handle": "string",
    "user": {
        "email": "string",
        "firstname": "string",
        "middlename": "string",
        "lastname": "string"
    },
    "title": "string",
    "created_at": "DateTime",
    "department_id": "reference",
    "job_template": {
        "created_at": "DateTime",
        "name": "string",
        "html": "string"
    },
    "description": "string",
    "salary": "float",
    "position_type": "reference",
    "city_id": "reference",
    "seniority": "reference",
    "industry_id": "reference",
    "is_published_on_widget": "boolean",
    "is_published_on_job_center": "boolean",
    "published_at": "DateTime",
    "requested_publication_at": "DateTime",
    "custom_fields": [
        {
            "custom_field_id": "reference",
            "values": [
                {
                    "id": "integer",
                    "value": "string"
                }
            ]
        }
    ],
    "finished_at": "DateTime",
    "start_of_work": "DateTime",
    "head_count": "integer",
    "apply_url": "string",
    "job_contents": [
        {
            "created_at": "DateTime",
            "content": "string"
        }
    ],
    "main_contact": "object (User)",
    "job_application_status_set": {
        "id": "integer",
        "statuses": [
            {
                "id": "integer",
                "name": "string",
                "abbreviation": "string",
                "is_default": "boolean",
                "is_rejected": "boolean",
                "is_hired": "boolean",
                "is_rejected_by_candidate": "boolean"
            }
        ]
    }
}
```

`PATCH /v1/job/{id}`
### Response codes
Response Code | Description
----------- | -----------
`200`|Returned on success
## List all custom fields in the application process of a specific job

> output on success

```json
{
    "data": [
        {
            "id": "integer",
            "name": "string",
            "label": "string",
            "possible_values": [
                {
                    "id": "integer",
                    "value": "string"
                }
            ],
            "is_job": "boolean",
            "is_candidate": "boolean"
        }
    ],
    "links": {
        "self": "string",
        "first": "string",
        "prev": "string",
        "next": "string",
        "last": "string"
    }
}
```

`GET /v1/job/{id}/custom_candidate_fields`
### Response codes
Response Code | Description
----------- | -----------
`200`|Returned on success
