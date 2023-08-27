# test-repo
test assignments 
Project: jobUrl
Description: this is rest full webservices using spring boot with jdk 1.8 where you can crawl github commits
Technologies and tools: spring boot 2.7.14, jdk 1.8 ,spring boot starter data jpa , spring boot starter web, web client, postman, postgres, maven, swagger ui
IDE: sts4
Endpoints: 1) http://localhost:8090/api/urlpost
method type : post
RequestBody Parameter: {
    "url": "your_url",
    "client_url_id": "your_client_url_id",
    "client_url_password": "your_client_url_password"
}
content : json
response: simple string as json
 2) http://localhost:8090/api/urljobrun 
 method type: post
 RequestBody Parameter: {
    "jobid": "your_jobid"
}
content : json
response: simple string as json

Database structure:
-- Table: public.datasave

-- DROP TABLE IF EXISTS public.datasave;

CREATE TABLE IF NOT EXISTS public.datasave
(
    ticket character varying(255) COLLATE pg_catalog."default",
    commit character varying(255) COLLATE pg_catalog."default",
    resource character varying(255) COLLATE pg_catalog."default",
    id character varying(255) COLLATE pg_catalog."default" NOT NULL,
    CONSTRAINT datasave_pkey PRIMARY KEY (id)
)

TABLESPACE pg_default;

ALTER TABLE IF EXISTS public.datasave
    OWNER to postgres;
-- Table: public.datajob

-- DROP TABLE IF EXISTS public.datajob;

CREATE TABLE IF NOT EXISTS public.datajob
(
    url character varying(255) COLLATE pg_catalog."default",
    client_url_id character varying(255) COLLATE pg_catalog."default",
    client_url_password character varying(255) COLLATE pg_catalog."default",
    jobid uuid NOT NULL,
    CONSTRAINT datajob_pkey PRIMARY KEY (jobid)
)

TABLESPACE pg_default;

ALTER TABLE IF EXISTS public.datajob
    OWNER to postgres;
-----------------------------------------------------------------------
swagger api endpointurl: http://localhost:8090/api/swagger-ui/index.html

