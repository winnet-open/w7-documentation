 
# API - http

The application has API for http REST and websocket

APIs documentation is compiled by routes handler declaration  and is located in running `microservices-api` at (for example) http://localhost:9002/api/v1/documentation.md

---


# API


## ETGTranscodifica   


### query  

  
**Require authentication and at least one grant of CONFIGURATION_OPERATOR,CONFIGURATION_ADMIN,CONFIGURATION_VIEW**

**methods** `GET`  
**url** `/api/v1/etgTranscodifica/list`




---


### insert  

  
**Require authentication and at least one grant of CONFIGURATION_OPERATOR,CONFIGURATION_ADMIN**

**methods** `POST`  
**url** `/api/v1/etgTranscodifica`




---


### update  

  
**Require authentication and at least one grant of CONFIGURATION_OPERATOR,CONFIGURATION_ADMIN**

**methods** `PUT`  
**url** `/api/v1/etgTranscodifica/:id`




---


### delete  

  
**Require authentication and at least one grant of CONFIGURATION_OPERATOR,CONFIGURATION_ADMIN**

**methods** `DELETE`  
**url** `/api/v1/etgTranscodifica/:id`




---


## alert   


### last  

Retrieve alerts in the last hours by now +24h  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/alert/list/from/:last`

### Request

#### params

- **:last** `int`  
  last hours  


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 

```json
{
  body:[
    {
      type:"alert",
      description:"alert entity"
    }
  ]
}
```

- **fail**

status 

```json
{
  body: {
    "ALERT_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/alert/list/from/1"
}
``` 
  
  - **response**  
    code ``  

```json
{
  body:{
  }
}
``` 




---


### zone  

Retrieve alert zone data as geojson file  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/alert/zone/:id`

### Request

#### params

- **:id** `int`  
  alert zone id  


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 

```json
{
  body:{
    type:"geojson",
    description:"geojson data of zone"
  }
}
```

- **fail**

status 

```json
{
  body: {
    "ALERT_ZONE_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/alert/zone/1"
}
``` 
  
  - **response**  
    code ``  

```json
{
  body:"[geojson data]"
}
``` 




---


### insert  

  
**Require authentication and at least one grant of GIS_ADMIN**

**methods** `POST`  
**url** `/api/v1/alert`




---


### delete  

  
**Require authentication and at least one grant of GIS_ADMIN**

**methods** `DELETE`  
**url** `/api/v1/alert/:id`




---


## analog   


### selectAllAnalog  

  
**Require authentication and at least one grant of CONFIGURATION_OPERATOR,CONFIGURATION_ADMIN,CONFIGURATION_VIEW**

**methods** `GET`  
**url** `/api/v1/analogs`




---


### insert  

  
**Require authentication and at least one grant of CONFIGURATION_OPERATOR,CONFIGURATION_ADMIN**

**methods** `POST`  
**url** `/api/v1/analog`




---


### update  

  
**Require authentication and at least one grant of CONFIGURATION_OPERATOR,CONFIGURATION_ADMIN**

**methods** `PUT`  
**url** `/api/v1/analog/:id`




---


### delete  

  
**Require authentication and at least one grant of CONFIGURATION_OPERATOR,CONFIGURATION_ADMIN**

**methods** `DELETE`  
**url** `/api/v1/analog/:id`




---


## archivio-allarmi   


### GET  

get alarms froms all station by user  
**Require authentication and at least one grant of ALARMS_VIEW**

**methods** `GET`  
**url** `/api/v1/alarmsModule`

### Request

#### params

- **:startAt** `timestamp`  
  unixtime (ms) time start  
- **:stopAt** `timestamp`  
  unixtime (ms) time stop  


#### header

- **Authentication** `[jwt token]`  





### Examples

- **successes**


  - **request**

```json
{
  url:"/alarmsModule?startAt=15188181&stopAt=8744865",
  header:{
    Authentication:"[jwt token]"
  }
}
``` 
  
  - **response**  
    code `200`  

```json
undefined
``` 




---


### GET  

get alarm by alarmId  
**Require authentication and at least one grant of ALARMS_VIEW**

**methods** `GET`  
**url** `/api/v1/alarmDetails/:alarmId`

### Request

#### params

- **:alarmId** `INT`  
  alarm id  


#### header

- **Authentication** `[jwt token]`  





### Examples

- **successes**


  - **request**

```json
{
  url:"/alarmDetails/136",
  header:{
    Authentication:"[jwt token]"
  }
}
``` 
  
  - **response**  
    code `200`  

```json
undefined
``` 




---


## areal-rain   


### query  

Retrieve all areal-rains  
**Require authentication and at least one grant of AREALRAIN_VIEW,AREALRAIN_ADMIN**

**methods** `GET`  
**url** `/api/v1/areal-rain/summaries`

### Request


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:[
    {
      type:"areal-rain",
      description:"areal-rain entity"
    }
  ]
}
```

- **fail**

status 404

```json
{
  body: {
    "ITEMS_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/areal-rain/list?startDate=1595010600000&endDate=1595014500000"
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:[
    {
      name:"LAMA BALICE",
      id:15,
      soglie:{
        id:15,
        pp_SAT_0_1:27,
        pp_SAT_0_3:36,
        pp_SAT_0_6:43,
        pp_SAT_0_12:51,
        pp_SAT_0_24:61,
        pp_SAT_1_1:32,
        pp_SAT_1_3:42,
        pp_SAT_1_6:50,
        pp_SAT_1_12:58,
        pp_SAT_1_24:69,
        pp_SAT_2_1:45,
        pp_SAT_2_3:57,
        pp_SAT_2_6:66,
        pp_SAT_2_12:76,
        pp_SAT_2_24:89,
        pp_MSAT_0_1:27,
        pp_MSAT_0_3:36,
        pp_MSAT_0_6:43,
        pp_MSAT_0_12:51,
        pp_MSAT_0_24:61,
        pp_MSAT_1_1:32,
        pp_MSAT_1_3:42,
        pp_MSAT_1_6:50,
        pp_MSAT_1_12:58,
        pp_MSAT_1_24:69,
        pp_MSAT_2_1:45,
        pp_MSAT_2_3:57,
        pp_MSAT_2_6:66,
        pp_MSAT_2_12:76,
        pp_MSAT_2_24:89,
        pp_ASC_0_1:27,
        pp_ASC_0_3:36,
        pp_ASC_0_6:43,
        pp_ASC_0_12:51,
        pp_ASC_0_24:61,
        pp_ASC_1_1:32,
        pp_ASC_1_3:42,
        pp_ASC_1_6:50,
        pp_ASC_1_12:58,
        pp_ASC_2_1:45,
        pp_ASC_2_3:57,
        pp_ASC_2_6:66,
        pp_ASC_2_12:76,
        pp_ASC_2_24:89
      },
      active:true,
      area:89.7,
      riduzioni:{
        k1:0,
        k3:0,
        k6:0,
        k12:0,
        k24:0
      },
      pp24Max:2.8740000544041386,
      pp12Max:2.8740000544041386,
      pp6Max:2.8740000544041386,
      pp3Max:2.8740000544041386,
      pp1Max:2.6508000510781993
    }
  ]
}
``` 




---


### query  

Retrieve all areal-rains  
**Require authentication and at least one grant of AREALRAIN_VIEW,AREALRAIN_ADMIN**

**methods** `GET`  
**url** `/api/v1/areal-rain/list`

### Request


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:[
    {
      type:"areal-rain",
      description:"areal-rain entity"
    }
  ]
}
```

- **fail**

status 404

```json
{
  body: {
    "ITEMS_NOT_FOUND"
  }  
}
```



---


### insertParam  

Insert Tiessen Param  
**Require authentication and at least one grant of AREALRAIN_ADMIN**

**methods** `POST`  
**url** `/api/v1/areal-rain/tiessenParam`




---


### updateParam  

Update Tiessen Param  
**Require authentication and at least one grant of AREALRAIN_ADMIN**

**methods** `PUT`  
**url** `/api/v1/areal-rain/tiessenParam`




---


### updateBasin  

Update basin info  
**Require authentication and at least one grant of AREALRAIN_ADMIN**

**methods** `PUT`  
**url** `/api/v1/areal-rain/tiessenBasin`




---


### updateSoglie  

Update thresholds basin  
**Require authentication and at least one grant of AREALRAIN_ADMIN**

**methods** `PUT`  
**url** `/api/v1/areal-rain/thresholdsBasin`




---


### insertSoglie  

Insert threshold basin  
**Require authentication and at least one grant of AREALRAIN_ADMIN**

**methods** `POST`  
**url** `/api/v1/areal-rain/thresholdsBasin`




---


### deleteSoglie  

Delete threshold basin  
**Require authentication and at least one grant of AREALRAIN_ADMIN**

**methods** `DELETE`  
**url** `/api/v1/areal-rain/thresholdsBasin/:id`




---


### deleteParam  

Delete Tiessen Param  
**Require authentication and at least one grant of AREALRAIN_ADMIN**

**methods** `DELETE`  
**url** `/api/v1/areal-rain/tiessenParam`




---


### insertBasin  

Insert basin info  
**Require authentication and at least one grant of AREALRAIN_ADMIN**

**methods** `POST`  
**url** `/api/v1/areal-rain/tiessenBasin`




---


### deleteBasin  

Insert basin info  
**Require authentication and at least one grant of AREALRAIN_ADMIN**

**methods** `POST`  
**url** `/api/v1/areal-rain/tiessenBasin/:id`




---


## auth   


### login  

Login in by username and password, get auth token  


**methods** `POST`  
**url** `/api/v1/login`

### Request



#### body


- **username** `string`  
  username  
- **password** `string`  
  username  




### Response

- **success**

status 200

```json
{
  body:{
    token:{
      type:"string",
      description:"jwt"
    },
    user:{
      type:"User",
      description:"user"
    }
  }
}
```

- **fail**

status 401

```json
{
  body: {
    "AUTH_LOGIN_ERROR"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  body:{
    username:"batman",
    password:"bruce12345"
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:{
    token:"[jwt token]"
  }
}
``` 


- **failures**


  - **request**

```json
{
  body:{
    username:"batman",
    password:"?"
  }
}
``` 
  
  - **response**  
    code `401`  

```json
{
  body:"AUTH_LOGIN_ERROR"
}
``` 



---


### session  

Retrieve current session by token  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/session`

### Request


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:{
    user:{
      type:"User",
      description:"user"
    }
  }
}
```

- **fail**

status 401

```json
{
  body: {
    "AUTH_INVALID_TOKEN"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/session",
  header:{
    Authentication:"[jwt token]"
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:{
    exp:1547231699,
    iat:1547123699,
    id:25,
    name:"Alessio",
    email:"alessio@etgsrl.it",
    username:"uffing",
    grants:[
      {
        id:1,
        stations:[
        ]
      },
      {
        id:2,
        stations:"*"
      },
      {
        id:3,
        stations:[
          1,
          2,
          3
        ]
      }
    ]
  }
}
``` 




---


### changePassword  

Update Password  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `POST`  
**url** `/api/v1/changePassword`

### Request



#### body


- **username** `string`  
  old  
- **password** `string`  
  new  




### Response

- **success**

status 200

```json
{
  body:{
    user:{
      type:"User",
      description:"user"
    }
  }
}
```

- **fail**

status 401

```json
{
  body: {
    "UPDATE_NOT_DONE"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  body:{
    old:"batman",
    new:"bruce12345"
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:{
    token:"[jwt token]"
  }
}
``` 


- **failures**


  - **request**

```json
{
  body:{
    old:"batman",
    new:"?"
  }
}
``` 
  
  - **response**  
    code `401`  

```json
{
  body:"UPDATE_NOT_DONE"
}
``` 



---


## camera   


### query  

Retrieve all cameras  
**Require authentication and at least one grant of CAMERA_VIEW,CAMERA_ADMIN,CAMERA_OPERATOR**

**methods** `GET`  
**url** `/api/v1/camera/list`

### Request


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:[
    {
      type:"camera",
      description:"camera entity"
    }
  ]
}
```

- **fail**

status 404

```json
{
  body: {
    "ITEMS_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/camera/list"
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:[
    {
      id:22,
      name:"Ponte Garibaldi 1",
      stationId:185,
      enabled:true,
      retrieve:2,
      model:null,
      group:""
    },
    {
      id:23,
      name:"Ponte Garibaldi 2",
      stationId:185,
      enabled:true,
      retrieve:3,
      model:null,
      group:""
    }
  ]
}
``` 




---


### get  

Retrieve a camera by id  
**Require authentication and at least one grant of CAMERA_VIEW,CAMERA_ADMIN,CAMERA_OPERATOR**

**methods** `GET`  
**url** `/api/v1/camera/:id`

### Request

#### params

- **:id** `int`  
  camera id - must be integer &gt; 0  


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 

```json
{
  body:{
    type:"camera",
    description:"camera entity"
  }
}
```

- **fail**

status 

```json
{
  body: {
    "CAMERA_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/camera/22"
}
``` 
  
  - **response**  
    code ``  

```json
{
  body:{
    id:22,
    name:"Ponte Garibaldi 1",
    stationId:185,
    enabled:true,
    retrieve:2,
    model:null,
    group:""
  }
}
``` 




---


### insert  

  
**Require authentication and at least one grant of CAMERA_ADMIN,CAMERA_OPERATOR**

**methods** `POST`  
**url** `/api/v1/camera`




---


### update  

  
**Require authentication and at least one grant of CAMERA_ADMIN,CAMERA_OPERATOR**

**methods** `PUT`  
**url** `/api/v1/camera/:id`




---


### delete  

  
**Require authentication and at least one grant of CAMERA_ADMIN,CAMERA_OPERATOR**

**methods** `DELETE`  
**url** `/api/v1/camera/:id`




---


### snapshots  

Retrieve last snapshots from a camera  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/camera/:id/snapshots/:last`

### Request

#### params

- **:id** `int`  
  camera id - must be integer &gt; 0  
- **:last** `int`  
  retrieve last snapshots  


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:[
    {
      type:"snapshot",
      description:"snapshot entity"
    }
  ]
}
```

- **fail**

status 404

```json
{
  body: {
    "ITEM_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  path:"/camera/22/snapshots/2"
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:[
    {
      id:57,
      cameraId:22,
      timestamp:1553774407040
    },
    {
      id:58,
      cameraId:22,
      timestamp:1553774407040
    }
  ]
}
``` 




---


### last-snapshots  

Retrieve last snapshot for every camera  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/camera/last-snapshots`

### Request


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:[
    {
      type:"snapshot",
      description:"snapshot entity"
    }
  ]
}
```

- **fail**

status 404

```json
{
  body: {
    "ITEM_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  path:"/camera/last-snapshots"
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:[
    {
      id:57,
      cameraId:22,
      timestamp:1553774407040
    },
    {
      id:58,
      cameraId:22,
      timestamp:1553774407040
    }
  ]
}
``` 




---


### snapshot-image  

Retrieve the snapshot image by id  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/camera/snapshot/:snapshotId`

### Request

#### params

- **:snapshotId** `int`  
  snapshot id - must be integer &gt; 0  


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:"[image]"
}
```

- **fail**

status 404

```json
{
  body: {
    "ITEM_NOT_FOUND"
  }  
}
```



---


### last-snapshot-image  

Retrieve the camera last snapshot image  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/camera/:id/last-snapshot`

### Request

#### params

- **:snapshotId** `int`  
  camera id - must be integer &gt; 0  


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:"[image]"
}
```

- **fail**

status 404

```json
{
  body: {
    "ITEM_NOT_FOUND"
  }  
}
```



---


### adiacent-snapshot  

Retrieve next or prev snapshot by snapshot id and camera  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/camera/snapshot/:snapshotId/:direction`

### Request

#### params

- **:snapshotId** `int`  
  snapshot id - must be integer &gt; 0  
- **:direction** `string`  
  prev or next, default prev  


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:{
    type:"snapshot",
    description:"snapshot entity"
  }
}
```

- **fail**

status 404

```json
{
  body: {
    "ITEM_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  path:"/camera/snapshot/951/prev"
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:{
    id:902,
    cameraId:22,
    timestamp:1553774407040
  }
}
``` 




---


## collection   


### get  

Retrieve data in date interval by station, sensor, measure from different sources/tables.  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `POST`  
**url** `/api/v1/collection/get`

### Request


#### header

- **Authentication** `[jwt token]`  


#### body


- **0** `[object Object]`  
    





### Examples

- **successes**


  - **request**

```json
{
  url:"/collection/get?start=1547510400000&end=1547518400000",
  header:{
    Authentication:"[jwt token]"
  },
  body:[
    {
      stationId:23,
      sensorId:5,
      measureId:5,
      type:"periodic"
    },
    {
      stationId:23,
      sensorId:0,
      measureId:9,
      type:"periodic"
    },
    {
      stationId:24,
      sensorId:0,
      measureId:9,
      type:"periodic"
    }
  ]
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:[
    {
      info:{
        stationId:23,
        sensorId:5,
        measureId:5,
        type:"periodic"
      },
      data:[
        {
          date:1547994600,
          value:2.4
        },
        {
          date:1547964600,
          value:2.5
        }
      ]
    },
    {
      info:{
        stationId:23,
        sensorId:0,
        measureId:9,
        type:"periodic"
      },
      data:[
        {
          date:1547994600,
          value:0
        },
        {
          date:1547964600,
          value:0
        }
      ]
    },
    {
      info:{
        stationId:24,
        sensorId:0,
        measureId:9,
        type:"periodic"
      },
      data:[
      ]
    }
  ]
}
``` 




---


### get  

Retrieve data in date interval by station, sensor, measure from different sources/tables.  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/collection/massive/get`



### Examples




---


### get  

Retrieve data in date interval by station, sensor, measure from different sources/tables.  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `POST`  
**url** `/api/v1/collection/massive/get`

### Request


#### header

- **Authentication** `[jwt token]`  


#### body


- **0** `[object Object]`  
    





### Examples

- **successes**


  - **request**

```json
{
  url:"/collection/massive/get?start=1547510400000&end=1547518400000",
  header:{
    Authentication:"[jwt token]"
  },
  body:[
    {
      stationId:23,
      sensorId:5,
      measureId:5,
      type:"periodic"
    },
    {
      stationId:23,
      sensorId:0,
      measureId:9,
      type:"periodic"
    },
    {
      stationId:24,
      sensorId:0,
      measureId:9,
      type:"periodic"
    }
  ]
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:[
    {
      info:{
        stationId:23,
        sensorId:5,
        measureId:5,
        type:"periodic"
      },
      data:[
        {
          date:1547994600,
          value:2.4
        },
        {
          date:1547964600,
          value:2.5
        }
      ]
    },
    {
      info:{
        stationId:23,
        sensorId:0,
        measureId:9,
        type:"periodic"
      },
      data:[
        {
          date:1547994600,
          value:0
        },
        {
          date:1547964600,
          value:0
        }
      ]
    },
    {
      info:{
        stationId:24,
        sensorId:0,
        measureId:9,
        type:"periodic"
      },
      data:[
      ]
    }
  ]
}
``` 




---


## configuration   


### query  

Retrieve alerts in the last hours by now +24h  
**Require authentication and at least one grant of DATAEXCHANGE_VIEW,DATAEXCHANGE_ADMIN**

**methods** `GET`  
**url** `/api/v1/configuration`




---


### get  

Retrieve alerts in the last hours by now +24h  
**Require authentication and at least one grant of DATAEXCHANGE_VIEW,DATAEXCHANGE_ADMIN**

**methods** `GET`  
**url** `/api/v1/configuration/:id`




---


### insert  

  
**Require authentication and at least one grant of DATAEXCHANGE_VIEW,DATAEXCHANGE_ADMIN**

**methods** `POST`  
**url** `/api/v1/configuration`




---


### delete  

  
**Require authentication and at least one grant of DATAEXCHANGE_VIEW,DATAEXCHANGE_ADMIN**

**methods** `DELETE`  
**url** `/api/v1/configuration/:id`




---


### update  

  
**Require authentication and at least one grant of DATAEXCHANGE_VIEW,DATAEXCHANGE_ADMIN**

**methods** `PUT`  
**url** `/api/v1/configuration/:id`




---


### getLogs  

  
**Require authentication and at least one grant of DATAEXCHANGE_VIEW,DATAEXCHANGE_ADMIN**

**methods** `GET`  
**url** `/api/v1/configuration/logs`




---


## digitin   


### query  

  
**Require authentication and at least one grant of CONFIGURATION_OPERATOR,CONFIGURATION_ADMIN,CONFIGURATION_VIEW**

**methods** `GET`  
**url** `/api/v1/digitin/list`




---


### insert  

  
**Require authentication and at least one grant of CONFIGURATION_OPERATOR,CONFIGURATION_ADMIN**

**methods** `POST`  
**url** `/api/v1/digitin`




---


### update  

  
**Require authentication and at least one grant of CONFIGURATION_OPERATOR,CONFIGURATION_ADMIN**

**methods** `PUT`  
**url** `/api/v1/digitin/:id`




---


### delete  

  
**Require authentication and at least one grant of CONFIGURATION_OPERATOR,CONFIGURATION_ADMIN**

**methods** `DELETE`  
**url** `/api/v1/digitin/:id`




---


## download   


### collection  

Download excel or csv file of collection data.  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `POST`  
**url** `/api/v1/download/collection`

### Request


#### header

- **Authentication** `[jwt token]`  


#### body


- **0** `[object Object]`  
    




### Response

- **success**

status 

```json
{
  body:"[excel or csv file]"
}
```

- **fail**

status 

```json
{
  body: {
    ""
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/collection/get?format=excel&start=1547510400000&end=1547518400000",
  header:{
    Authentication:"[jwt token]"
  },
  body:[
    {
      stationId:23,
      sensorId:5,
      measureId:5,
      type:"periodic"
    },
    {
      stationId:23,
      sensorId:0,
      measureId:9,
      type:"periodic"
    },
    {
      stationId:24,
      sensorId:0,
      measureId:9,
      type:"periodic"
    }
  ]
}
``` 
  
  - **response**  
    code ``  

```json
{
  body:"[excel file]"
}
``` 




---


### windrose  

Download excel or csv file of station windrose data.  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `POST`  
**url** `/api/v1/download/windrose/:stationId/:type`

### Request

#### params

- **:stationId** `int`  
  station id - must be integer &gt; 0  
- **:type** `string`  
  daily or periodic  


#### header

- **Authentication** `[jwt token]`  


#### body


- **speeds** ``  
    




### Response

- **success**

status 

```json
{
  body:"[excel or csv file]"
}
```

- **fail**

status 

```json
{
  body: {
    ""
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/download/station/windrose/207/periodic?start=1547510400000&end=1547518400000",
  header:{
    Authentication:"[jwt token]"
  },
  body:{
    speeds:[
      [
        0,
        0.5
      ],
      [
        0.5,
        2
      ],
      [
        2,
        null
      ]
    ]
  }
}
``` 
  
  - **response**  
    code ``  

```json
{
  body:"[excel file]"
}
``` 




---


## external   


### query  

Retrieve station list  
**Require authentication and at least one grant of EXTERNAL_SERVICES_VIEW**

**methods** `GET`  
**url** `/api/v1/externalServices/station/list`

### Request





### Response

- **success**

status 200

```json
{
  body:[
    {
      type:"Station",
      description:"Station entity"
    }
  ]
}
```

- **fail**

status 

```json
{
  body: {
    ""
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/externalServices/station/list"
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:[
    {
      id:17,
      name:"Metauro",
      city:"Lucrezia",
      municipality:"Cartoceto",
      subbasin:"Metauro",
      basin:"Metauro",
      river:"Metauro",
      province:"PU",
      latitude:43.7626,
      longitude:12.967533333333334,
      flags:"NORMAL",
      altitude:36,
      sensors:[
        {
          id:0,
          description:"Pioggia TOT Oggi",
          unit:"mm",
          measures:{
            daily:[
              9
            ],
            periodic:[
              9
            ]
          }
        },
        {
          id:1,
          description:"IntensitÃ  Pioggia",
          unit:"mm/min",
          measures:{
            daily:[
              3
            ],
            periodic:[
              3
            ]
          }
        },
        {
          id:5,
          description:"Temperatura Aria",
          unit:"Â°C",
          measures:{
            daily:[
              1,
              3,
              5
            ],
            periodic:[
              1,
              3,
              5
            ]
          }
        },
        {
          id:6,
          description:"UmiditÃ  Relativa",
          unit:"%",
          measures:{
            daily:[
              1,
              3,
              5
            ],
            periodic:[
              1,
              3,
              5
            ]
          }
        },
        {
          id:100,
          description:"Livello Metauro",
          unit:"mt",
          measures:{
            daily:[
              1,
              3,
              5
            ],
            periodic:[
              1,
              3,
              5,
              8
            ]
          }
        },
        {
          id:300,
          description:"Tensione Batteria",
          unit:"Volt",
          measures:{
            daily:[
              1
            ],
            periodic:[
              3,
              5
            ]
          }
        },
        {
          id:305,
          description:"Quality Level",
          unit:"%",
          measures:{
            daily:[
              1,
              3
            ],
            periodic:[
            ]
          }
        }
      ],
      inputs:[
        {
          id:1016,
          description:"Alimentazione TLC",
          bit:17
        },
        {
          id:1011,
          description:"Power Save Mode",
          bit:9
        }
      ]
    }
  ],
  sensors:[
    {
      id:0,
      description:"Pioggia totale Oggi",
      unit:"mm"
    }
  ],
  measures:[
    {
      id:1,
      description:"Valore Minimo",
      code:"MIN"
    }
  ],
  layers:[
    {
      id:8,
      name:"Zone allerta valanghe"
    }
  ]
}
``` 




---


### current  

Retrieve current sensor values for station from last hours  
**Require authentication and at least one grant of EXTERNAL_SERVICES_VIEW**

**methods** `GET`  
**url** `/api/v1/externalServices/current/:stationId/:sensorId/:last`

### Request

#### params

- **:stationId** `int`  
  station id - must be integer &gt; 0  
- **:sensorId** `int`  
  sensor id - must be integer &gt; 0  
- **:last** `int`  
  retrieve from last hours - must be integer &gt; 0  


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:[
    {
      date:{
        type:"unixtime",
        description:"last sensor value update (ms)"
      },
      value:{
        type:"number",
        description:"value from sensor"
      },
      last:{
        type:"int",
        description:"hours past from sensor value"
      }
    }
  ]
}
```

- **fail**

status 404

```json
{
  body: {
    "_DATA_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/externalServices/current/5/0/1",
  header:{
    Authentication:"[jwt token]"
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:[
    {
      date:1544076090000,
      value:0,
      last:1
    },
    {
      date:1544076192000,
      value:0,
      last:1
    },
    {
      date:1544076322000,
      value:0,
      last:1
    }
  ]
}
``` 




---


### station-history-rain  

get station history rain  
**Require authentication and at least one grant of EXTERNAL_SERVICES_VIEW**

**methods** `GET`  
**url** `/api/v1/externalServices/station/history-rain/:date`

### Request


#### header

- **Authentication** `[jwt token]`  


#### body






### Response

- **success**

status 200

```json
{
  body:[
    {
      id:"int",
      lastUpdate:"int",
      history:{
        rain:{
          "6":"int",
          "12":"int",
          "24":"int",
          "48":"int",
          "96":"int"
        }
      }
    }
  ]
}
```

- **fail**

status 404

```json
{
  body: {
    "ITEM_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/externalServices/station/history-rain/1581379200000",
  header:{
    Authentication:"[jwt token]"
  },
  body:{
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:[
    {
      id:1,
      lastUpdate:1580460670143,
      history:{
        rain:{
          "6":0,
          "12":0.2,
          "24":0.2,
          "48":0.2,
          "96":1.8
        }
      }
    },
    {
      id:2,
      lastUpdate:1580482270143,
      history:{
        rain:{
          "1":0,
          "3":0,
          "6":0,
          "12":0.2,
          "24":0.2,
          "48":0.2,
          "96":1.8
        }
      }
    }
  ]
}
``` 




---


### login  

Login in by username and password, get auth token  


**methods** `POST`  
**url** `/api/v1/externalServices/login`

### Request



#### body


- **username** `string`  
  username  
- **password** `string`  
  username  




### Response

- **success**

status 200

```json
{
  body:{
    token:{
      type:"string",
      description:"jwt"
    },
    user:{
      type:"User",
      description:"user"
    }
  }
}
```

- **fail**

status 401

```json
{
  body: {
    "AUTH_LOGIN_ERROR"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  body:{
    username:"batman",
    password:"bruce12345"
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:{
    token:"[jwt token]"
  }
}
``` 


- **failures**


  - **request**

```json
{
  body:{
    username:"batman",
    password:"?"
  }
}
``` 
  
  - **response**  
    code `401`  

```json
{
  body:"AUTH_LOGIN_ERROR"
}
``` 



---


## fer   


### query  

Retrieve fer Info  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/fers`

### Request





### Response

- **success**

status 200

```json
{
  body:[
    {
      id:{
        type:"string",
        description:"Fer Code"
      },
      flags:{
        type:"string",
        description:"Fer Flags"
      },
      description:{
        type:"string",
        description:"Fer description"
      },
      fault:{
        type:"int",
        description:"Fer fault - could be 1 (fault) or 0 (not fault)"
      },
      latitude:{
        type:"string",
        description:"Fer latitude"
      },
      longitude:{
        type:"string",
        description:"Fer longitude"
      },
      priority:{
        type:"int",
        description:"Fer connection priority"
      },
      sibling:{
        type:"string",
        description:"Fer code of sibling"
      }
    }
  ]
}
```

- **fail**

status 500

```json
{
  body: {
    ""
  }  
}
```



---


## graphProfile   


### insert  

save graph profile  
**Require authentication and at least one grant of GIS_OPERATOR,GIS_ADMIN**

**methods** `POST`  
**url** `/api/v1/profile/graph`

### Request


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 201

```json
{
  body:[
    {
      type:"Graph Profile",
      description:"Graph Profile entity"
    }
  ]
}
```

- **fail**

status 409

```json
{
  body: {
    "ITEM_NOT_INSERTED"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/profile/graph",
  body:[
    {
      name:"Ancona Rain",
      public:true,
      default:false,
      data:"...json"
    }
  ]
}
``` 
  
  - **response**  
    code `201`  

```json
{
  body:[
    {
      id:43,
      name:"Ancona Rain",
      ownerId:101,
      public:true,
      default:false,
      data:"...json"
    }
  ]
}
``` 




---


### get  

get graph profile by id  
**Require authentication and at least one grant of GIS_OPERATOR,GIS_ADMIN**

**methods** `GET`  
**url** `/api/v1/profile/graph/:id`

### Request


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:[
    {
      type:"Graph Profile",
      description:"Graph Profile entity"
    }
  ]
}
```

- **fail**

status 404

```json
{
  body: {
    "ITEM_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/profile/graph/43"
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:[
    {
      id:43,
      name:"Ancona Rain",
      ownerId:101,
      public:true,
      default:false,
      data:"...json"
    }
  ]
}
``` 




---


### query  

get all graph profile  
**Require authentication and at least one grant of GIS_OPERATOR,GIS_ADMIN**

**methods** `GET`  
**url** `/api/v1/profile/graph`

### Request


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:[
    {
      type:"Graph Profile",
      description:"Graph Profile entity"
    }
  ]
}
```

- **fail**

status 404

```json
{
  body: {
    "ITEMS_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/profile/graph"
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:[
    {
      id:43,
      name:"Ancona Rain",
      ownerId:101,
      public:true,
      default:false,
      data:"...json"
    },
    {
      id:17,
      name:"Ancona Wind",
      ownerId:101,
      public:true,
      default:false,
      data:"...json"
    },
    {
      id:3,
      name:"Bari Rain",
      ownerId:101,
      public:true,
      default:false,
      data:"...json"
    }
  ]
}
``` 




---


### delete  

delete graph profile by id  
**Require authentication and at least one grant of GIS_OPERATOR,GIS_ADMIN**

**methods** `DELETE`  
**url** `/api/v1/profile/graph/:id`

### Request


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:[
    {
      type:"Graph Profile",
      description:"Graph Profile entity"
    }
  ]
}
```

- **fail**

status 409

```json
{
  body: {
    "ITEM_NOT_DELETED"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/profile/graph/43"
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:[
  ]
}
``` 




---


### update  

update graph profile by id  
**Require authentication and at least one grant of GIS_OPERATOR,GIS_ADMIN**

**methods** `PUT`  
**url** `/api/v1/profile/graph/:id`

### Request


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:[
    {
      type:"Graph Profile",
      description:"Graph Profile entity"
    }
  ]
}
```

- **fail**

status 409

```json
{
  body: {
    "ITEM_NOT_UPDATED"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/profile/graph/43",
  body:[
    {
      name:"Ancona Rain",
      public:true,
      default:false,
      data:"...json"
    }
  ]
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:[
    {
      id:43,
      name:"Ancona Rain",
      ownerId:101,
      public:true,
      default:false,
      data:"...json"
    }
  ]
}
``` 




---


## layer   


### get  

Retrieve a layer by id  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/layer/:id`

### Request

#### params

- **:id** `int`  
  layer id - must be integer &gt; 0  


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 

```json
{
  body:{
    id:{
      type:"int",
      description:"layer id"
    },
    name:{
      type:"string",
      description:"layer name"
    },
    data:{
      type:"geojson",
      description:"geojson data of layer"
    }
  }
}
```

- **fail**

status 

```json
{
  body: {
    "LAYER_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/layer/1"
}
``` 
  
  - **response**  
    code ``  

```json
{
  body:{
    id:1,
    name:"Bacini idrografici",
    data:"[geojson data]"
  }
}
``` 




---


### query  

Retrieve all layers  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/layer/list`

### Request


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 

```json
{
  body:[
    {
      id:{
        type:"int",
        description:"layer id"
      },
      name:{
        type:"string",
        description:"layer name"
      }
    }
  ]
}
```

- **fail**

status 

```json
{
  body: {
    "LAYERS_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/layer/list"
}
``` 
  
  - **response**  
    code ``  

```json
{
  body:[
    {
      id:1,
      name:"Bacini idrografici"
    },
    {
      id:2,
      name:"Confini comunali"
    },
    {
      id:3,
      name:"Confini provinciali"
    }
  ]
}
``` 




---


### insert  

save layer  
**Require authentication and at least one grant of GIS_ADMIN,GIS_OPERATOR**

**methods** `POST`  
**url** `/api/v1/layer`

### Request


#### header

- **Authentication** `[jwt token]`  


#### body


- **type** ``  
    
- **file** `file`  
  file to upload  
- **name** `string`  
  name of file  




### Response

- **success**

status 201

```json
{
  body:[
    {
      id:{
        type:"number",
        description:"id layer inserted"
      },
      data:{
        file:{
          type:"string",
          description:"name file"
        },
        mime:{
          type:"string",
          description:"type application"
        }
      },
      name:{
        type:"string",
        description:"layer name"
      },
      allowDelete:{
        type:"boolean",
        description:"permission layer delete"
      }
    }
  ]
}
```

- **fail**

status 409

```json
{
  body: {
    "ITEM_NOT_INSERTED"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/layer"
}
``` 
  
  - **response**  
    code `201`  

```json
{
  body:[
    {
      id:6,
      name:"custom-Confini",
      data:{
        file:"custom-Confini",
        mime:"application/octet-stream"
      },
      allowDelete:true
    }
  ]
}
``` 




---


### delete  

delete layer  
**Require authentication and at least one grant of GIS_ADMIN,GIS_OPERATOR**

**methods** `DELETE`  
**url** `/api/v1/layer/:id`

### Request


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:[
  ]
}
```

- **fail**

status 409

```json
{
  body: {
    "ITEM_NOT_DELETED"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/layer/5"
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:[
  ]
}
``` 




---


## logsActivity   


### query  

  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/logsActivity`




---


### insert  

  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `POST`  
**url** `/api/v1/logsActivity`




---


## main   


### test  

  


**methods** `GET`  
**url** `/api/v1/test`




---


### settings  

Retrieve server APIs, described in this document  


**methods** `GET`  
**url** `/api/v1/settings`

### Request





### Response

- **success**

status 200

```json
{
  body:[
    {
      "[entity]":{
        type:"object",
        description:"Entity",
        "[action]":{
          type:"object",
          description:"Entity action",
          method:{
            type:"string",
            description:"http method (get, post, put, delete ...)"
          },
          url:{
            type:"string",
            description:"http url"
          }
        }
      }
    }
  ]
}
```

- **fail**

status 

```json
{
  body: {
    ""
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/settings"
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:{
    auth:{
      login:{
        method:"POST",
        url:"/api/v1/login"
      },
      session:{
        method:"GET",
        url:"/api/v1/session"
      }
    },
    layer:{
      get:{
        method:"GET",
        url:"/api/v1/layer/:id"
      },
      query:{
        method:"GET",
        url:"/api/v1/layer/list"
      }
    }
  }
}
``` 




---


### references  

Retrieve app immutable data of core entities  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/references`

### Request


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:{
    maps:[
      {
        type:"Map",
        description:"Map entity"
      }
    ],
    inputs:[
      {
        type:"Input",
        description:"input entity"
      }
    ],
    stations:[
      {
        type:"Station",
        description:"Station entity"
      }
    ],
    sensors:[
      {
        type:"Sensor",
        description:"Sensor entity"
      }
    ],
    measures:[
      {
        type:"Measure",
        description:"Measure entity"
      }
    ],
    layers:[
      {
        type:"Layer",
        description:"Layer entity"
      }
    ],
    grants:[
      {
        type:"Grant",
        description:"Grant entity"
      }
    ],
    fer:[
      {
        type:"Fer",
        description:"Fer service fer.query"
      }
    ]
  }
}
```

- **fail**

status 

```json
{
  body: {
    ""
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/references"
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:{
    maps:[
      {
        name:"Wikimedia",
        link:"https://microservice-map/map/wikimedia/osm-intl/{z}/{x}/{y}{r}.png?apikey={apikey}",
        apikey:"test",
        attribution:"<a href=\"https://wikimediafoundation.org/wiki/Maps_Terms_of_Use\">Wikimedia</a>"
      }
    ],
    inputs:[
      {
        id:1000,
        description:"Alimentazione Radio"
      }
    ],
    stations:[
      {
        id:17,
        name:"Metauro",
        city:"Lucrezia",
        municipality:"Cartoceto",
        subbasin:"Metauro",
        basin:"Metauro",
        river:"Metauro",
        province:"PU",
        latitude:43.7626,
        longitude:12.967533333333334,
        flags:"NORMAL",
        altitude:36,
        sensors:[
          {
            id:0,
            description:"Pioggia TOT Oggi",
            unit:"mm",
            measures:{
              daily:[
                9
              ],
              periodic:[
                9
              ]
            }
          },
          {
            id:1,
            description:"IntensitÃ  Pioggia",
            unit:"mm/min",
            measures:{
              daily:[
                3
              ],
              periodic:[
                3
              ]
            }
          },
          {
            id:5,
            description:"Temperatura Aria",
            unit:"Â°C",
            measures:{
              daily:[
                1,
                3,
                5
              ],
              periodic:[
                1,
                3,
                5
              ]
            }
          },
          {
            id:6,
            description:"UmiditÃ  Relativa",
            unit:"%",
            measures:{
              daily:[
                1,
                3,
                5
              ],
              periodic:[
                1,
                3,
                5
              ]
            }
          },
          {
            id:100,
            description:"Livello Metauro",
            unit:"mt",
            measures:{
              daily:[
                1,
                3,
                5
              ],
              periodic:[
                1,
                3,
                5,
                8
              ]
            }
          },
          {
            id:300,
            description:"Tensione Batteria",
            unit:"Volt",
            measures:{
              daily:[
                1
              ],
              periodic:[
                3,
                5
              ]
            }
          },
          {
            id:305,
            description:"Quality Level",
            unit:"%",
            measures:{
              daily:[
                1,
                3
              ],
              periodic:[
              ]
            }
          }
        ],
        inputs:[
          {
            id:1016,
            description:"Alimentazione TLC",
            bit:17
          },
          {
            id:1011,
            description:"Power Save Mode",
            bit:9
          }
        ]
      }
    ],
    sensors:[
      {
        id:0,
        description:"Pioggia totale Oggi",
        unit:"mm"
      }
    ],
    measures:[
      {
        id:1,
        description:"Valore Minimo",
        code:"MIN"
      }
    ],
    layers:[
      {
        id:8,
        name:"Zone allerta valanghe"
      }
    ],
    grants:{
      "1":{
        code:"[STATION_VIEW]",
        description:"Vedi stazioni"
      },
      "2":{
        code:"[STATION_EDIT]",
        description:"Modifica stazioni"
      }
    }
  }
}
``` 




---


### documentation  

this file  


**methods** `GET`  
**url** `/api/v1/documentation:ext(.*)`



### Examples

- **successes**


  - **request**

```json
{
  url:"/documentation"
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:"markdown documentation (this file)"
}
``` 

  - **request**

```json
{
  url:"/documentation.md"
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:"markdown documentation (this file)"
}
``` 




---


## profile   


### query  

Retrieve all profiles  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/profile/list`

### Request


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:[
    {
      type:"Profile",
      description:"Profile entity"
    }
  ]
}
```

- **fail**

status 404

```json
{
  body: {
    "ITEMS_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/profile/list"
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:[
    {
      id:43,
      name:"Ancona Rain",
      ownerId:101,
      public:true,
      default:false,
      data:"...json"
    }
  ]
}
``` 




---


### get  

Retrieve a profile by id  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/profile/:id`

### Request

#### params

- **:id** `int`  
  profile id - must be integer &gt; 0  


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:{
    type:"Profile",
    description:"Profile entity"
  }
}
```

- **fail**

status 404

```json
{
  body: {
    "ITEM_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/profile/1"
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:{
    id:43,
    name:"Ancona Rain",
    ownerId:101,
    public:true,
    default:false,
    data:"...json"
  }
}
``` 




---


### insert  

  
**Require authentication and at least one grant of GIS_OPERATOR,GIS_ADMIN**

**methods** `POST`  
**url** `/api/v1/profile`




---


### update  

  
**Require authentication and at least one grant of GIS_OPERATOR,GIS_ADMIN**

**methods** `PUT`  
**url** `/api/v1/profile/:id`




---


### delete  

  
**Require authentication and at least one grant of GIS_OPERATOR,GIS_ADMIN**

**methods** `DELETE`  
**url** `/api/v1/profile/:id`




---


## sarpam   


### query  

Retrieve sarpam Info  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/sarpams`

### Request





### Response

- **success**

status 200

```json
{
  body:[
    {
      id:{
        type:"string",
        description:"Fer Code"
      },
      flags:{
        type:"string",
        description:"Fer Flags"
      },
      description:{
        type:"string",
        description:"Fer description"
      },
      fault:{
        type:"int",
        description:"Fer fault - could be 1 (fault) or 0 (not fault)"
      },
      latitude:{
        type:"string",
        description:"Fer latitude"
      },
      longitude:{
        type:"string",
        description:"Fer longitude"
      },
      priority:{
        type:"int",
        description:"Fer connection priority"
      },
      sibling:{
        type:"string",
        description:"Fer code of sibling"
      }
    }
  ]
}
```

- **fail**

status 500

```json
{
  body: {
    ""
  }  
}
```



---


## station-comands   


### getdati  

Send command to http for station  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `POST`  
**url** `/api/v1/commands/station-data/:fer`

### Request

#### params

- **:fer** `string`  
  fer to call  


#### header

- **Authentication** `[jwt token]`  





### Examples

- **successes**


  - **request**

```json
{
  path:"/api/commands/station-data/F12"
}
``` 
  
  - **response**  
    code ``  

```json
{
  body:{
    message:[
      {
        codstaz:85,
        analog:{
          flags:"C000",
          sensore:5,
          valore:0,
          trend:1
        },
        digitin:{
          tipodigi:1006,
          valore:0
        }
      }
    ]
  }
}
``` 




---


## station-info   


### get  

Retrieve station info  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/station/:id/info`

### Request

#### params

- **:id** `int`  
  station id - must be integer &gt; 0  


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:{
    name:{
      type:"string",
      description:"name"
    },
    city:{
      type:"string",
      description:"city"
    },
    municipality:{
      type:"string",
      description:"municipality"
    },
    subbasin:{
      type:"string",
      description:"subbasin"
    },
    basin:{
      type:"string",
      description:"basin"
    },
    river:{
      type:"string",
      description:"river"
    },
    province:{
      type:"string",
      description:"province"
    },
    altitude:{
      type:"int",
      description:"altitude"
    },
    notes:{
      type:"string",
      description:"notes"
    },
    latitude:{
      type:"number",
      description:"latitude in decimal degrees"
    },
    longitude:{
      type:"number",
      description:"longitude in decimal degrees"
    },
    stsconf:{
      type:"string",
      description:"stations configuration"
    }
  }
}
```

- **fail**

status 404

```json
{
  body: {
    "ITEM_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/station/123/info",
  header:{
    Authentication:"[jwt token]"
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:{
    name:"Chienti 1",
    city:"Divina Pastora",
    municipality:"Tolentino",
    subbasin:"Chienti",
    basin:"N.D.",
    river:"Chienti",
    province:"MC",
    altitude:0,
    notes:"",
    latitude:43.2323,
    longitude:13.371133333333335,
    stsconf:"<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<STAZ ID=\"010\" ... </STAZ>"
  }
}
``` 




---


### update  

Update station info - only the fields in request  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `PUT`  
**url** `/api/v1/station/:id/info`

### Request

#### params

- **:id** `int`  
  station id - must be integer &gt; 0  


#### header

- **Authentication** `[jwt token]`  


#### body


- **name** `string`  
  name  
- **city** `string`  
  city  
- **municipality** `string`  
  municipality  
- **subbasin** `string`  
  subbasin  
- **basin** `string`  
  basin  
- **river** `string`  
  river  
- **province** `string`  
  province  
- **altitude** `int`  
  altitude  
- **notes** `string`  
  notes  
- **latitude** `number`  
  latitude in decimal degrees  
- **longitude** `number`  
  longitude in decimal degrees  
- **stsconf** `string`  
  stations configuration  




### Response

- **success**

status 200

```json
{
  body:""
}
```

- **fail**

status 409

```json
{
  body: {
    "ITEM_NOT_UPDATED"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/station/123/info",
  header:{
    Authentication:"[jwt token]"
  },
  body:{
    stsconf:"<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<STAZ ID=\"010\" ... </STAZ>"
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:""
}
``` 




---


## station-memo   


### query  

Retrieve all memo for station  
**Require authentication and at least one grant of STATION_MEMO_VIEW,STATION_MEMO_OPERATOR**

**methods** `GET`  
**url** `/api/v1/station/:stationId/memo/list`

### Request

#### params

- **:stationId** `int`  
  station id - must be integer &gt; 0  


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:[
    {
      sensorId:{
        type:"int",
        description:"sensor id"
      },
      value:{
        type:"float",
        description:"value"
      },
      date:{
        type:"timestamp",
        description:"unixtime (ms) date"
      },
      event:{
        type:"string",
        description:"event"
      },
      priority:{
        type:"int",
        description:"priority"
      },
      notes:{
        type:"string",
        description:"notes"
      }
    }
  ]
}
```

- **fail**

status 404

```json
{
  body: {
    "ITEMS_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/station/123/memo/list",
  header:{
    Authentication:"[jwt token]"
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:[
    {
      sensorId:123,
      value:4.56,
      date:1547510400000,
      event:"Evento ...",
      priority:2,
      notes:""
    }
  ]
}
``` 




---


### get  

Retrieve single memo by id  
**Require authentication and at least one grant of STATION_MEMO_VIEW,STATION_MEMO_OPERATOR**

**methods** `GET`  
**url** `/api/v1/station/:stationId/memo/:id`

### Request

#### params

- **:stationId** `int`  
  station id - must be integer &gt; 0  
- **:id** `int`  
  memo id - must be integer &gt; 0  


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:{
    sensorId:{
      type:"int",
      description:"sensor id"
    },
    value:{
      type:"float",
      description:"value"
    },
    date:{
      type:"timestamp",
      description:"unixtime (ms) date"
    },
    event:{
      type:"string",
      description:"event"
    },
    priority:{
      type:"int",
      description:"priority"
    },
    notes:{
      type:"string",
      description:"notes"
    }
  }
}
```

- **fail**

status 404

```json
{
  body: {
    "ITEM_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/station/123/memo/56",
  header:{
    Authentication:"[jwt token]"
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:{
    sensorId:123,
    value:4.56,
    date:1547510400000,
    event:"Evento ...",
    priority:2,
    notes:""
  }
}
``` 




---


### insert  

Insert memo to a station  
**Require authentication and at least one grant of STATION_MEMO_OPERATOR**

**methods** `POST`  
**url** `/api/v1/station/:stationId/memo`

### Request

#### params

- **:stationId** `int`  
  station id - must be integer &gt; 0  


#### header

- **Authentication** `[jwt token]`  


#### body


- **sensorId** `int`  
  sensor id  
- **value** `float`  
  value  
- **date** `timestamp`  
  unixtime (ms) date  
- **event** `string`  
  event  
- **priority** `int`  
  priority  
- **notes** `string`  
  notes  




### Response

- **success**

status 201

```json
{
  body:{
    id:{
      type:"int",
      description:"memo id inserted"
    }
  }
}
```

- **fail**

status 409

```json
{
  body: {
    "ITEM_NOT_INSERTED"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/station/123/memo",
  header:{
    Authentication:"[jwt token]"
  },
  body:{
    sensorId:99,
    value:11.22,
    date:1547510400000,
    event:"Evento ...",
    priority:2,
    notes:""
  }
}
``` 
  
  - **response**  
    code `201`  

```json
{
  body:{
    id:78
  }
}
``` 




---


### update  

Update station memo - only the fields in request  
**Require authentication and at least one grant of STATION_MEMO_OPERATOR**

**methods** `PUT`  
**url** `/api/v1/station/:stationId/memo/:id`

### Request

#### params

- **:stationId** `int`  
  station id - must be integer &gt; 0  
- **:id** `int`  
  memo id - must be integer &gt; 0  


#### header

- **Authentication** `[jwt token]`  


#### body


- **sensorId** `int`  
  sensor id  
- **value** `float`  
  value  
- **date** `timestamp`  
  unixtime (ms) date  
- **event** `string`  
  event  
- **priority** `int`  
  priority  
- **notes** `string`  
  notes  




### Response

- **success**

status 200

```json
{
  body:""
}
```

- **fail**

status 409

```json
{
  body: {
    "ITEM_NOT_UPDATED"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/station/123/memo/78",
  header:{
    Authentication:"[jwt token]"
  },
  body:{
    sensorId:21,
    value:12.99,
    date:1547510400000,
    event:"Evento ...",
    priority:2,
    notes:""
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:""
}
``` 




---


### delete  

  
**Require authentication and at least one grant of STATION_MEMO_OPERATOR**

**methods** `DELETE`  
**url** `/api/v1/station/:stationId/memo/:id`




---


### getStationsMemo  

  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `POST`  
**url** `/api/v1/stations/memo`




---


## station-telnet   


### command  

Send command to telent for station  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/station/:id/telnet/:command`

### Request

#### params

- **:id** `int`  
  station id - must be integer &gt; 0  
- **:command** `string`  
  telnet command: can be &quot;getdati&quot;, &quot;getstato&quot;, &quot;getconfig&quot;  


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 

```json
{
  body:{
    message:{
      type:"string",
      description:"Telnet response"
    }
  }
}
```

- **fail**

status 

```json
{
  body: {
    "STATION_UNREACHABLE"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  path:"/station/11/telnet/getdati"
}
``` 
  
  - **response**  
    code ``  

```json
{
  body:{
    message:"[OK] ..."
  }
}
``` 




---


### reboot  

Send command &quot;reboot [station] [param]&quot; to telent  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/station/:id/telnet/reboot/:param`

### Request

#### params

- **:id** `int`  
  station id - must be integer &gt; 0  
- **:param** `int`  
  reboot param, can be one of 1,2,4,8,16,32  


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 

```json
{
  body:{
    message:{
      type:"string",
      description:"Telnet response"
    }
  }
}
```

- **fail**

status 

```json
{
  body: {
    "STATION_UNREACHABLE"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  path:"/station/11/telnet/reboot/1"
}
``` 
  
  - **response**  
    code ``  

```json
{
  body:{
    message:"[OK] ..."
  }
}
``` 




---


### setconfig  

Send command &quot;setconfig [station]&quot; to telent  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `PUT`  
**url** `/api/v1/station/:id/telnet/setconfig`

### Request

#### params

- **:id** `int`  
  station id - must be integer &gt; 0  


#### header

- **Authentication** `[jwt token]`  


#### body


- **stsconf** `string`  
  stsconf  




### Response

- **success**

status 

```json
{
  body:{
    message:{
      type:"string",
      description:"Telnet response"
    }
  }
}
```

- **fail**

status 

```json
{
  body: {
    "STATION_UNREACHABLE"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  path:"/station/11/telnet/setconfig",
  body:{
    stsconf:"<XML ..."
  }
}
``` 
  
  - **response**  
    code ``  

```json
{
  body:{
    message:"[OK] ..."
  }
}
``` 




---


## station   


### query  

Retrieve station list  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/station/list`

### Request





### Response

- **success**

status 200

```json
{
  body:[
    {
      type:"Station",
      description:"Station entity"
    }
  ]
}
```

- **fail**

status 

```json
{
  body: {
    ""
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/station/list"
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:[
    {
      id:17,
      name:"Metauro",
      city:"Lucrezia",
      municipality:"Cartoceto",
      subbasin:"Metauro",
      basin:"Metauro",
      river:"Metauro",
      province:"PU",
      latitude:43.7626,
      longitude:12.967533333333334,
      flags:"NORMAL",
      altitude:36,
      sensors:[
        {
          id:0,
          description:"Pioggia TOT Oggi",
          unit:"mm",
          measures:{
            daily:[
              9
            ],
            periodic:[
              9
            ]
          }
        },
        {
          id:1,
          description:"IntensitÃ  Pioggia",
          unit:"mm/min",
          measures:{
            daily:[
              3
            ],
            periodic:[
              3
            ]
          }
        },
        {
          id:5,
          description:"Temperatura Aria",
          unit:"Â°C",
          measures:{
            daily:[
              1,
              3,
              5
            ],
            periodic:[
              1,
              3,
              5
            ]
          }
        },
        {
          id:6,
          description:"UmiditÃ  Relativa",
          unit:"%",
          measures:{
            daily:[
              1,
              3,
              5
            ],
            periodic:[
              1,
              3,
              5
            ]
          }
        },
        {
          id:100,
          description:"Livello Metauro",
          unit:"mt",
          measures:{
            daily:[
              1,
              3,
              5
            ],
            periodic:[
              1,
              3,
              5,
              8
            ]
          }
        },
        {
          id:300,
          description:"Tensione Batteria",
          unit:"Volt",
          measures:{
            daily:[
              1
            ],
            periodic:[
              3,
              5
            ]
          }
        },
        {
          id:305,
          description:"Quality Level",
          unit:"%",
          measures:{
            daily:[
              1,
              3
            ],
            periodic:[
            ]
          }
        }
      ],
      inputs:[
        {
          id:1016,
          description:"Alimentazione TLC",
          bit:17
        },
        {
          id:1011,
          description:"Power Save Mode",
          bit:9
        }
      ]
    }
  ],
  sensors:[
    {
      id:0,
      description:"Pioggia totale Oggi",
      unit:"mm"
    }
  ],
  measures:[
    {
      id:1,
      description:"Valore Minimo",
      code:"MIN"
    }
  ],
  layers:[
    {
      id:8,
      name:"Zone allerta valanghe"
    }
  ]
}
``` 




---


### current  

Retrieve current sensor values for station from last hours  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/current/:stationId/:sensorId/:last`

### Request

#### params

- **:stationId** `int`  
  station id - must be integer &gt; 0  
- **:sensorId** `int`  
  sensor id - must be integer &gt; 0  
- **:last** `int`  
  retrieve from last hours - must be integer &gt; 0  


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:[
    {
      date:{
        type:"unixtime",
        description:"last sensor value update (ms)"
      },
      value:{
        type:"number",
        description:"value from sensor"
      },
      last:{
        type:"int",
        description:"hours past from sensor value"
      }
    }
  ]
}
```

- **fail**

status 404

```json
{
  body: {
    "_DATA_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/current/5/0/1",
  header:{
    Authentication:"[jwt token]"
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:[
    {
      date:1544076090000,
      value:0,
      last:1
    },
    {
      date:1544076192000,
      value:0,
      last:1
    },
    {
      date:1544076322000,
      value:0,
      last:1
    }
  ]
}
``` 




---


### windrose  

Retrieve wind speed and quadrant angle (0-15) for station in time interval.  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `POST`  
**url** `/api/v1/station/windrose/:stationId/:type`

### Request

#### params

- **:stationId** `int`  
  station id - must be integer &gt; 0  
- **:type** `string`  
  daily or periodic  


#### header

- **Authentication** `[jwt token]`  


#### body


- **speeds** ``  
    




### Response

- **success**

status 200

```json
{
  body:[
    {
      range:[
        0,
        0.5
      ],
      quote:10.5,
      data:[
        {
          type:"int",
          description:"wind angle quadrant 0-15"
        },
        {
          type:"float",
          description:"wind angle speed"
        }
      ]
    }
  ]
}
```

- **fail**

status 404

```json
{
  body: {
    "WINDROSE_DATA_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/station/windrose/207/periodic?start=1547510400000&end=1547518400000",
  header:{
    Authentication:"[jwt token]"
  },
  body:{
    speeds:[
      [
        0,
        0.5
      ],
      [
        0.5,
        2
      ],
      [
        2,
        null
      ]
    ]
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:[
    {
      speeds:[
        0,
        0.5
      ],
      data:[
        [
          0,
          1.81
        ],
        [
          1,
          0.62
        ],
        [
          2,
          0.82
        ],
        [
          3,
          0.59
        ],
        [
          4,
          0.62
        ],
        [
          5,
          1.22
        ],
        [
          6,
          1.61
        ],
        [
          7,
          2.04
        ],
        [
          8,
          2.66
        ],
        [
          9,
          2.96
        ],
        [
          10,
          2.53
        ],
        [
          11,
          1.97
        ],
        [
          12,
          1.64
        ],
        [
          13,
          1.32
        ],
        [
          14,
          1.58
        ],
        [
          15,
          1.51
        ]
      ]
    },
    {
      speeds:[
        0.5,
        2
      ],
      data:[
        [
          0,
          1.81
        ],
        [
          1,
          0.62
        ],
        [
          2,
          0.82
        ],
        [
          3,
          0.59
        ],
        [
          4,
          0.62
        ],
        [
          5,
          1.22
        ],
        [
          6,
          1.61
        ],
        [
          7,
          2.04
        ],
        [
          8,
          2.66
        ],
        [
          9,
          2.96
        ],
        [
          10,
          2.53
        ],
        [
          11,
          1.97
        ],
        [
          12,
          1.64
        ],
        [
          13,
          1.32
        ],
        [
          14,
          1.58
        ],
        [
          15,
          1.51
        ]
      ]
    },
    {
      speeds:[
        2,
        null
      ],
      data:[
        [
          0,
          1.81
        ],
        [
          1,
          0.62
        ],
        [
          2,
          0.82
        ],
        [
          3,
          0.59
        ],
        [
          4,
          0.62
        ],
        [
          5,
          1.22
        ],
        [
          6,
          1.61
        ],
        [
          7,
          2.04
        ],
        [
          8,
          2.66
        ],
        [
          9,
          2.96
        ],
        [
          10,
          2.53
        ],
        [
          11,
          1.97
        ],
        [
          12,
          1.64
        ],
        [
          13,
          1.32
        ],
        [
          14,
          1.58
        ],
        [
          15,
          1.51
        ]
      ]
    }
  ]
}
``` 




---


### alarm-limit-get  

Retrieve station alarm limit  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/alarm/limit`

### Request


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:{
    "[stationId]":{
      "[sensorId]":"[data json]"
    }
  }
}
```

- **fail**

status 404

```json
{
  body: {
    "ALARM_LIMIT_DATA_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/alarm/limit?stationId=9",
  header:{
    Authentication:"[jwt token]"
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:{
    "9":{
      "100":{
        AlarmL:{
          value:14
        },
        AlarmH:{
          value:9
        }
      },
      "104":{
        AlarmL:{
          value:14.7
        },
        AlarmH:{
          value:18.6
        }
      }
    }
  }
}
``` 




---


### alarm-limit-insert  

Insert station alarm limit records; update if record exists  
**Require authentication and at least one grant of GIS_OPERATOR,GIS_ADMIN**

**methods** `POST`  
**url** `/api/v1/alarm/limit`

### Request


#### header

- **Authentication** `[jwt token]`  


#### body


```json
{
  "[stationId]":{
    "[sensorId]":"[data json]"
  }
}
```




### Response

- **success**

status 201

```json
{
  body:""
}
```

- **fail**

status 409

```json
{
  body: {
    "ITEM_NOT_INSERTED"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/alarm/limit",
  header:{
    Authentication:"[jwt token]"
  },
  body:{
    "5":{
      "100":{
        AlarmL:{
          value:14
        },
        AlarmH:{
          value:9
        }
      },
      "104":{
        AlarmL:{
          value:14.7
        },
        AlarmH:{
          value:18.6
        }
      }
    },
    "9":{
      "100":{
        AlarmL:{
          value:14
        },
        AlarmH:{
          value:9
        }
      },
      "104":{
        AlarmL:{
          value:14.7
        },
        AlarmH:{
          value:18.6
        }
      }
    }
  }
}
``` 
  
  - **response**  
    code `201`  

```json
{
  body:""
}
``` 




---


### alarm-limit-update  

Replace station alarm limit records for stations  
**Require authentication and at least one grant of GIS_OPERATOR,GIS_ADMIN**

**methods** `PUT`  
**url** `/api/v1/alarm/limit`

### Request


#### header

- **Authentication** `[jwt token]`  


#### body


```json
{
  "[stationId]":{
    "[sensorId]":"[data json]"
  }
}
```




### Response

- **success**

status 200

```json
{
  body:""
}
```

- **fail**

status 409

```json
{
  body: {
    "ITEM_NOT_UPDATED"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/alarm/limit",
  header:{
    Authentication:"[jwt token]"
  },
  body:{
    "5":{
      "100":{
        AlarmL:{
          value:14
        },
        AlarmH:{
          value:9
        }
      },
      "104":{
        AlarmL:{
          value:14.7
        },
        AlarmH:{
          value:18.6
        }
      }
    },
    "9":{
      "100":{
        AlarmL:{
          value:14
        },
        AlarmH:{
          value:9
        }
      },
      "104":{
        AlarmL:{
          value:14.7
        },
        AlarmH:{
          value:18.6
        }
      }
    }
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:""
}
``` 




---


### alarm-limit-delete  

Delete station alarm limit records for stations  
**Require authentication and at least one grant of GIS_OPERATOR,GIS_ADMIN**

**methods** `DELETE`  
**url** `/api/v1/alarm/limit`

### Request


#### header

- **Authentication** `[jwt token]`  


#### body


- **stations** ``  
    




### Response

- **success**

status 200

```json
{
  body:""
}
```

- **fail**

status 409

```json
{
  body: {
    "ITEM_NOT_DELETED"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/alarm/limit",
  header:{
    Authentication:"[jwt token]"
  },
  body:{
    stationIds:[
      9,
      5,
      10
    ]
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:""
}
``` 




---


### picture-get  

Retrieve the station picture  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/station/:stationId/picture`

### Request

#### params

- **:stationId** `int`  
  station id - must be integer &gt; 0  


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:"[image]"
}
```

- **fail**

status 404

```json
{
  body: {
    "ITEM_NOT_FOUND"
  }  
}
```



---


### picture-insert  

Upload picture station, replace if already exists  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `POST`  
**url** `/api/v1/station/:stationId/picture`

### Request

#### params

- **:stationId** `int`  
  station id - must be integer &gt; 0  


#### header

- **Authentication** `[jwt token]`  


#### body


- **picture** ``  
    




### Response

- **success**

status 201

```json
{
  body:""
}
```

- **fail**

status 409

```json
{
  body: {
    "ITEM_NOT_INSERTED"
  }  
}
```



---


### picture-delete  

Delete picture station  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `DELETE`  
**url** `/api/v1/station/:stationId/picture`

### Request

#### params

- **:stationId** `int`  
  station id - must be integer &gt; 0  


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:""
}
```

- **fail**

status 409

```json
{
  body: {
    "ITEM_NOT_DELETED"
  }  
}
```



---


### periodic  

Retrieve periodic sensor values for station from last hours  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/periodic/:stationId/:sensorId/:last`

### Request

#### params

- **:stationId** `int`  
  station id - must be integer &gt; 0  
- **:sensorId** `int`  
  sensor id - must be integer &gt; 0  
- **:last** `int`  
  retrieve from last hours - must be integer &gt; 0  


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:[
    {
      date:{
        type:"unixtime",
        description:"last sensor value update (ms)"
      },
      value:{
        type:"number",
        description:"value from sensor"
      },
      last:{
        type:"int",
        description:"hours past from sensor value"
      }
    }
  ]
}
```

- **fail**

status 404

```json
{
  body: {
    "_DATA_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/periodic/5/0/1",
  header:{
    Authentication:"[jwt token]"
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:[
    {
      date:1544076090000,
      value:0,
      last:1
    },
    {
      date:1544076192000,
      value:0,
      last:1
    },
    {
      date:1544076322000,
      value:0,
      last:1
    }
  ]
}
``` 




---


### station-history-rain  

get station history rain  
**Require authentication and at least one grant of GIS_OPERATOR,GIS_ADMIN,GIS_VIEW**

**methods** `GET`  
**url** `/api/v1/station/history-rain/:date`

### Request


#### header

- **Authentication** `[jwt token]`  


#### body






### Response

- **success**

status 200

```json
{
  body:[
    {
      id:"int",
      lastUpdate:"int",
      history:{
        rain:{
          "6":"int",
          "12":"int",
          "24":"int",
          "48":"int",
          "96":"int"
        }
      }
    }
  ]
}
```

- **fail**

status 404

```json
{
  body: {
    "ITEM_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/station/history-rain/1581379200000",
  header:{
    Authentication:"[jwt token]"
  },
  body:{
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:[
    {
      id:1,
      lastUpdate:1580460670143,
      history:{
        rain:{
          "6":0,
          "12":0.2,
          "24":0.2,
          "48":0.2,
          "96":1.8
        }
      }
    },
    {
      id:2,
      lastUpdate:1580482270143,
      history:{
        rain:{
          "1":0,
          "3":0,
          "6":0,
          "12":0.2,
          "24":0.2,
          "48":0.2,
          "96":1.8
        }
      }
    }
  ]
}
``` 




---


### intensive-insert  

Insert station alarm limit records; update if record exists  
**Require authentication and at least one grant of ALARMS_OPERATOR,ALARMS_ADMIN**

**methods** `POST`  
**url** `/api/v1/alarm-limit/intensive`

### Request


#### header

- **Authentication** `[jwt token]`  


#### body






### Response

- **success**

status 201

```json
{
  body:{
  }
}
```

- **fail**

status 409

```json
{
  body: {
    "ITEM_NOT_INSERTED"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/alarm-limit/intensive",
  header:{
    Authentication:"[jwt token]"
  },
  body:{
    "5":{
      "3":{
        alarm:null,
        warn:5,
        orange:null
      },
      "6":{
        alarm:null,
        warn:5,
        orange:null
      },
      "12":{
        alarm:null,
        warn:5,
        orange:null
      },
      "24":{
        alarm:null,
        warn:5,
        orange:null
      }
    },
    "9":{
      "3":{
        alarm:null,
        warn:5,
        orange:null
      },
      "6":{
        alarm:null,
        warn:5,
        orange:null
      },
      "12":{
        alarm:null,
        warn:5,
        orange:null
      },
      "24":{
        alarm:null,
        warn:5,
        orange:null
      }
    }
  }
}
``` 
  
  - **response**  
    code `201`  

```json
{
  body:{
  }
}
``` 




---


### intensive-delete  

Delete station alarm limit records for stations and sensor 0  
**Require authentication and at least one grant of ALARMS_OPERATOR,ALARMS_ADMIN**

**methods** `DELETE`  
**url** `/api/v1/alarm-limit/intensive/:id`

### Request


#### header

- **Authentication** `[jwt token]`  


#### body


- **stations** ``  
    




### Response

- **success**

status 200

```json
{
  body:""
}
```

- **fail**

status 409

```json
{
  body: {
    "ITEM_NOT_DELETED"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/alarm-limit/intensive/5",
  header:{
    Authentication:"[jwt token]"
  },
  body:{
    stationIds:[
      9,
      5,
      10
    ]
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:""
}
``` 




---


### intensive-get  

Delete station alarm limit records for stations and sensor 0  
**Require authentication and at least one grant of ALARMS_OPERATOR,ALARMS_ADMIN,ALARMS_VIEW**

**methods** `GET`  
**url** `/api/v1/alarm-limit/intensive`

### Request


#### header

- **Authentication** `[jwt token]`  


#### body


- **stations** ``  
    




### Response

- **success**

status 200

```json
{
  body:""
}
```

- **fail**

status 404

```json
{
  body: {
    "ITEM_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/alarm-limit/intensive",
  header:{
    Authentication:"[jwt token]"
  },
  body:{
    stationIds:[
      9,
      5,
      10
    ]
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:""
}
``` 




---


### batteryLevel-get  

get min battery level   
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/stations/minBatteryYesterday`

### Request


#### header

- **Authentication** `[jwt token]`  


#### body






### Response

- **success**

status 200

```json
{
  body:[
    {
      "[idStation]":"value"
    },
    {
      "[idStation]":"value"
    }
  ]
}
```

- **fail**

status 404

```json
{
  body: {
    "ITEM_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/stations/minBatteryYesterday",
  header:{
    Authentication:"[jwt token]"
  },
  body:{
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:[
    {
      "1":14.077818
    },
    {
      "2":12.926
    }
  ]
}
``` 




---


### getSTSCONF  

get alarm limit configuration  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/alarm-limit/getSTSCONF`

### Request


#### header

- **Authentication** `[jwt token]`  


#### body






### Response

- **success**

status 200

```json
{
  body:[
    {
      "[idStation]":{
        "[idSensor]":{
          alarm_h:"value",
          warn_h:"value",
          isteresi:"value",
          limmin:"-value",
          limmax:"value",
          limvar:"value",
          deadtime:"value"
        }
      }
    },
    {
      "[idStation]":{
        "[idSensor]":{
          alarm_h:"value",
          warn_h:"value",
          isteresi:"value",
          limmin:"-value",
          limmax:"value",
          limvar:"value",
          deadtime:"value"
        }
      }
    }
  ]
}
```

- **fail**

status 404

```json
{
  body: {
    "ITEMS_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/alarm-limit/getSTSCONF",
  header:{
    Authentication:"[jwt token]"
  },
  body:{
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:[
    {
      "1":{
        "100":{
          limmin:-0.51,
          limmax:5.25,
          limvar:0.1,
          warn_l:-5,
          warn_h:0.5,
          alarm_l:-5,
          alarm_h:1,
          deadtime:600,
          isteresi:0.1
        }
      },
      "2":{
        "100":{
          limmin:-1.23,
          limmax:3.75,
          limvar:0.1,
          warn_l:-5,
          warn_h:1.5,
          alarm_l:-5,
          alarm_h:2,
          deadtime:600,
          isteresi:0.1
        }
      }
    }
  ]
}
``` 




---


### update  

Update station  
**Require authentication and at least one grant of CONFIGURATION_OPERATOR,CONFIGURATION_ADMIN**

**methods** `PUT`  
**url** `/api/v1/station/:id`

### Request

#### params

- **:id** `int`  
  station id - must be integer &gt; 0  


#### header

- **Authentication** `[jwt token]`  


#### body


- **name** `string`  
  name  
- **city** `string`  
  city  
- **municipality** `string`  
  municipality  
- **subbasin** `string`  
  subbasin  
- **basin** `string`  
  basin  
- **river** `string`  
  river  
- **province** `string`  
  province  
- **altitude** `int`  
  altitude  
- **notes** `string`  
  notes  
- **latitude** `number`  
  latitude in decimal degrees  
- **longitude** `number`  
  longitude in decimal degrees  
- **stsconf** `string`  
  stations configuration  




### Response

- **success**

status 200

```json
{
  body:""
}
```

- **fail**

status 409

```json
{
  body: {
    "ITEM_NOT_UPDATED"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/station/123",
  header:{
    Authentication:"[jwt token]"
  },
  body:{
    stsconf:"<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<STAZ ID=\"010\" ... </STAZ>"
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:""
}
``` 




---


### insert  

Insert station  
**Require authentication and at least one grant of CONFIGURATION_OPERATOR,CONFIGURATION_ADMIN**

**methods** `POST`  
**url** `/api/v1/station`

### Request

#### params

- **:id** `int`  
  station id - must be integer &gt; 0  


#### header

- **Authentication** `[jwt token]`  


#### body


- **name** `string`  
  name  
- **city** `string`  
  city  
- **municipality** `string`  
  municipality  
- **subbasin** `string`  
  subbasin  
- **basin** `string`  
  basin  
- **river** `string`  
  river  
- **province** `string`  
  province  
- **altitude** `int`  
  altitude  
- **notes** `string`  
  notes  
- **latitude** `number`  
  latitude in decimal degrees  
- **longitude** `number`  
  longitude in decimal degrees  
- **stsconf** `string`  
  stations configuration  




### Response

- **success**

status 201

```json
{
  body:""
}
```

- **fail**

status 409

```json
{
  body: {
    "ITEM_NOT_INSERTED"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/station/123",
  header:{
    Authentication:"[jwt token]"
  },
  body:{
    stsconf:"<?xml version=\"1.0\" encoding=\"UTF-8\"?>\n<STAZ ID=\"010\" ... </STAZ>"
  }
}
``` 
  
  - **response**  
    code `201`  

```json
{
  body:""
}
``` 




---


### delete  

Delete station  
**Require authentication and at least one grant of CONFIGURATION_OPERATOR,CONFIGURATION_ADMIN**

**methods** `DELETE`  
**url** `/api/v1/station/:id`

### Request

#### params

- **:id** `int`  
  station id - must be integer &gt; 0  


#### header

- **Authentication** `[jwt token]`  


#### body






### Response

- **success**

status 200

```json
{
  body:""
}
```

- **fail**

status 409

```json
{
  body: {
    "ITEM_NOT_DELETED"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/station/123",
  header:{
    Authentication:"[jwt token]"
  },
  body:{
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:""
}
``` 




---


## storicData   


### uploadStoricData  

  
**Require authentication and at least one grant of CONFIGURATION_ADMIN,CONFIGURATION_OPERATOR**

**methods** `POST`  
**url** `/api/v1/uploadStoricData`




---


## storicUpdate   


### query  

  
**Require authentication and at least one grant of CONFIGURATION_OPERATOR,CONFIGURATION_ADMIN,CONFIGURATION_VIEW**

**methods** `GET`  
**url** `/api/v1/storicUpdate/list`




---


### insert  

  
**Require authentication and at least one grant of CONFIGURATION_OPERATOR,CONFIGURATION_ADMIN**

**methods** `POST`  
**url** `/api/v1/storicUpdate`




---


### update  

  
**Require authentication and at least one grant of CONFIGURATION_OPERATOR,CONFIGURATION_ADMIN**

**methods** `PUT`  
**url** `/api/v1/storicUpdate/:id`




---


### delete  

  
**Require authentication and at least one grant of CONFIGURATION_OPERATOR,CONFIGURATION_ADMIN**

**methods** `DELETE`  
**url** `/api/v1/storicUpdate/:id`




---


## user   


### query  

Retrieve all users  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/user/list`

### Request


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:[
    {
      type:"user",
      description:"user entity"
    }
  ]
}
```

- **fail**

status 404

```json
{
  body: {
    "ITEMS_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/user/list"
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:[
    {
      id:1,
      name:"Giuseppe",
      username:"giuseppe-verdi",
      email:"giuseppe.verdi@gmail.com",
      grants:[
        {
          id:1,
          stations:[
          ]
        },
        {
          id:2,
          stations:"*"
        },
        {
          id:3,
          stations:[
            1,
            2,
            3
          ]
        }
      ],
      enabled:true
    },
    {
      id:2,
      name:"Francesca",
      username:"francesca-rossi",
      email:"francesca-rossi@gmail.com",
      grants:[
        {
          id:2,
          stations:"*"
        }
      ],
      enabled:false
    }
  ]
}
``` 




---


### get  

Retrieve a user by id  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/user/:id`

### Request

#### params

- **:id** `int`  
  user id - must be integer &gt; 0  


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:{
    type:"user",
    description:"user entity"
  }
}
```

- **fail**

status 404

```json
{
  body: {
    "ITEM_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/user/2"
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:{
    id:2,
    name:"Francesca",
    username:"francesca-rossi",
    email:"francesca-rossi@gmail.com",
    grants:[
      {
        id:2,
        stations:"*"
      }
    ],
    enabled:true
  }
}
``` 




---


### insert  

  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `POST`  
**url** `/api/v1/user`




---


### update  

  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `PUT`  
**url** `/api/v1/user/:id`




---


### delete  

  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `DELETE`  
**url** `/api/v1/user/:id`




---


### scale-graph-get  

Retrieve user graphs scale  
**Require authentication and at least one grant of GIS_VIEW,GRAPH_VIEW**

**methods** `GET`  
**url** `/api/v1/scale/graph`

### Request


#### header

- **Authentication** `[jwt token]`  




### Response

- **success**

status 200

```json
{
  body:{
    "[stationId]":{
      "[sensorId]":{
        "[measureId]":{
          min:{
            type:"number",
            description:"min value"
          },
          max:{
            type:"number",
            description:"max value"
          }
        }
      }
    }
  }
}
```

- **fail**

status 404

```json
{
  body: {
    "GRAPH_SCALE_DATA_NOT_FOUND"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/scale/graph?stationId=9",
  header:{
    Authentication:"[jwt token]"
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:{
    "1":{
      "100":{
        "1":{
          min:-1,
          max:4
        },
        "3":{
          min:-1,
          max:4
        },
        "5":{
          min:-1,
          max:4
        },
        "8":{
          min:-1,
          max:4
        },
        "17":{
          min:-1,
          max:4
        }
      }
    }
  }
}
``` 




---


### scale-graph-insert  

Insert user graphs scale records; update if record exists  
**Require authentication and at least one grant of GRAPH_OPERATOR,GRAPH_ADMIN**

**methods** `POST`  
**url** `/api/v1/scale/graph`

### Request


#### header

- **Authentication** `[jwt token]`  


#### body


```json
{
  "[stationId]":{
    "[sensorId]":{
      "[measureId]":{
        min:{
          type:"number",
          description:"min value"
        },
        max:{
          type:"number",
          description:"max value"
        }
      }
    }
  }
}
```




### Response

- **success**

status 201

```json
{
  body:""
}
```

- **fail**

status 409

```json
{
  body: {
    "ITEM_NOT_INSERTED"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/scale/graph",
  header:{
    Authentication:"[jwt token]"
  },
  body:{
    "5":{
      "100":{
        "1":{
          min:-1,
          max:4
        },
        "3":{
          min:0,
          max:7
        },
        "5":{
          min:1,
          max:9
        },
        "8":{
          min:2,
          max:10
        }
      }
    },
    "9":{
      "100":{
        "1":{
          min:-1,
          max:4
        },
        "3":{
          min:0,
          max:7
        },
        "5":{
          min:1,
          max:9
        },
        "8":{
          min:2,
          max:10
        }
      }
    }
  }
}
``` 
  
  - **response**  
    code `201`  

```json
{
  body:""
}
``` 




---


### scale-graph-update  

Replace user graphs scale records for stations  
**Require authentication and at least one grant of GRAPH_OPERATOR,GRAPH_ADMIN**

**methods** `PUT`  
**url** `/api/v1/scale/graph`

### Request


#### header

- **Authentication** `[jwt token]`  


#### body


```json
{
  "[stationId]":{
    "[sensorId]":{
      "[measureId]":{
        min:{
          type:"number",
          description:"min value"
        },
        max:{
          type:"number",
          description:"max value"
        }
      }
    }
  }
}
```




### Response

- **success**

status 200

```json
{
  body:""
}
```

- **fail**

status 409

```json
{
  body: {
    "ITEM_NOT_UPDATED"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/scale/graph",
  header:{
    Authentication:"[jwt token]"
  },
  body:{
    "5":{
      "100":{
        "2":{
          min:-1,
          max:4
        }
      }
    },
    "9":{
      "100":{
        "1":{
          min:-1,
          max:4
        }
      }
    }
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:""
}
``` 




---


### scale-graph-delete  

Delete user graphs scale records for stations  
**Require authentication and at least one grant of GRAPH_OPERATOR,GRAPH_ADMIN**

**methods** `DELETE`  
**url** `/api/v1/scale/graph`

### Request


#### header

- **Authentication** `[jwt token]`  


#### body


- **stations** ``  
    




### Response

- **success**

status 200

```json
{
  body:""
}
```

- **fail**

status 409

```json
{
  body: {
    "ITEM_NOT_DELETED"
  }  
}
```


### Examples

- **successes**


  - **request**

```json
{
  url:"/scale/graph",
  header:{
    Authentication:"[jwt token]"
  },
  body:{
    stationIds:[
      9,
      5,
      10
    ]
  }
}
``` 
  
  - **response**  
    code `200`  

```json
{
  body:""
}
``` 




---


## Entities


### map

Schema

```json
{
  name:{
    type:"string",
    description:"name"
  },
  link:{
    type:"string",
    description:"http link to microservice-map with params placeholder in {}"
  },
  apikey:{
    type:"string",
    description:"apikey for link field"
  },
  attribution:{
    type:"string",
    description:"a label, usually terms of use"
  }
}
``` 

Example 

```json
{
  name:"Wikimedia",
  link:"https://dev-w7.braceslab.com/map/wikimedia/osm-intl/{z}/{x}/{y}{r}.png?apikey={apikey}",
  apikey:"test",
  attribution:"<a href=\"https://wikimediafoundation.org/wiki/Maps_Terms_of_Use\">Wikimedia</a>"
}
``` 


### input

Schema

```json
{
  id:{
    type:"int",
    description:"id"
  },
  description:{
    type:"string",
    description:"description"
  },
  bit:{
    type:"int",
    description:"events bit"
  }
}
``` 

Example 

```json
{
  id:1000,
  description:"Alimentazione Radio"
}
``` 


### station

Schema

```json
{
  id:{
    type:"int",
    description:"id"
  },
  name:{
    type:"string",
    description:"name"
  },
  city:{
    type:"string",
    description:"city"
  },
  municipality:{
    type:"string",
    description:"municipality"
  },
  subbasin:{
    type:"string",
    description:"subbasin"
  },
  basin:{
    type:"string",
    description:"basin"
  },
  river:{
    type:"string",
    description:"river"
  },
  province:{
    type:"string",
    description:"province"
  },
  latitude:{
    type:"number",
    description:"latitude in decimal degrees"
  },
  longitude:{
    type:"number",
    description:"longitude in decimal degrees"
  },
  flags:{
    type:"enum",
    description:"stations status, can be NOT_CALLED or NORMAL"
  },
  altitude:{
    type:"int",
    description:"altitude"
  },
  radio:{
    type:"string",
    description:"radio"
  },
  transmission:{
    type:"string",
    description:"transmission"
  },
  sensors:{
    type:"Sensor",
    description:"list of sensors in station"
  },
  inputs:{
    type:"Input",
    description:"list of inputs in station"
  }
}
``` 

Example 

```json
{
  id:9,
  name:"Potenza 1",
  city:"San Severino Marche",
  municipality:"San Severino Marche",
  subbasin:"Potenza",
  basin:"N.D.",
  river:"Potenza",
  province:"MC",
  latitude:43.22946666666667,
  longitude:13.18845,
  flags:"NORMAL",
  altitude:220,
  sensors:{
  }
}
``` 


### sensor

Schema

```json
{
  id:{
    type:"int",
    description:"id"
  },
  description:{
    type:"string",
    description:"description"
  },
  unit:{
    type:"string",
    description:"Measure unit"
  },
  decimal:{
    type:"int",
    description:"Number of decimal"
  },
  measures:{
    daily:[
      {
        type:"int",
        description:"Measure id"
      }
    ],
    periodic:[
      {
        type:"int",
        description:"Measure id"
      }
    ]
  }
}
``` 

Example 

```json
{
  id:0,
  description:"Pioggia totale Oggi",
  unit:"mm",
  measures:{
    daily:[
      9
    ],
    periodic:[
      9
    ]
  }
}
``` 


### measure

Schema

```json
{
  id:{
    type:"int",
    description:"id"
  },
  description:{
    type:"string",
    description:"description"
  },
  code:{
    type:"string",
    description:"Code"
  }
}
``` 

Example 

```json
{
  id:1,
  description:"Valore Minimo",
  code:"MIN"
}
``` 


### layer

Schema

```json
{
  id:{
    type:"int",
    description:"layer id"
  },
  name:{
    type:"string",
    description:"layer name"
  }
}
``` 

Example 

```json
{
  id:8,
  name:"Zone allerta valanghe"
}
``` 


### user

Schema

```json
{
  exp:{
    type:"int",
    description:"expire unixtime"
  },
  grants:{
    type:"array",
    description:"grants"
  },
  id:{
    type:"int",
    description:"user id"
  },
  iat:{
    type:"int",
    description:"same as ext, used in session"
  },
  email:{
    type:"string",
    description:"email"
  },
  name:{
    type:"string",
    description:"name"
  },
  username:{
    type:"string",
    description:"username"
  },
  enabled:{
    type:"boolean",
    description:"enabled"
  }
}
``` 

Example 

```json
{
  id:25,
  name:"Alessio",
  email:"alessio@etgsrl.it",
  username:"alessio",
  grants:[
    {
      id:1,
      stations:null
    },
    {
      id:2,
      stations:null
    }
  ]
}
``` 


### grant

Schema

```json
{
  id:{
    type:"int",
    description:"id"
  },
  code:{
    type:"string",
    description:"code"
  },
  description:{
    type:"string",
    description:"description"
  }
}
``` 

Example 

```json
{
  id:1,
  code:"[STATION_VIEW]",
  description:"Vedi stazioni"
}
``` 


### profile

Schema

```json
{
  id:{
    type:"int",
    description:"id"
  },
  name:{
    type:"string",
    description:"name"
  },
  ownerId:{
    type:"int",
    description:"user.id profile owner"
  },
  public:{
    type:"bool",
    description:"profile is public or private"
  },
  default:{
    type:"int",
    description:"profile is the default for the user"
  },
  data:{
    type:"json",
    description:"json data"
  }
}
``` 

Example 

```json
{
  id:43,
  name:"Ancona Rain",
  ownerId:101,
  public:true,
  default:false,
  data:"...json"
}
``` 


### camera

Schema

```json
{
  id:{
    type:"int",
    description:"id"
  },
  name:{
    type:"string",
    description:"name"
  },
  stationId:{
    type:"int",
    description:"station id"
  },
  enabled:{
    type:"bool",
    description:"camera is enabled for retrieve"
  },
  retrieve:{
    type:"int",
    description:"scheduled retrieve minutes, 0-60, ex. 15 = every 15 min"
  },
  model:{
    type:"string",
    description:"camera model"
  },
  group:{
    type:"group",
    description:"camera group - usually means is the same camera that rotate to takes different snapshot"
  }
}
``` 

Example 

```json
{
  id:23,
  name:"Ponte Garibaldi",
  stationId:185,
  enabled:true,
  retrieve:15,
  model:null
}
``` 


### snapshot

Schema

```json
{
  id:{
    type:"int",
    description:"id"
  },
  cameraId:{
    type:"int",
    description:"camera id"
  },
  timestamp:{
    type:"timestamp",
    description:"timestamp"
  }
}
``` 

Example 

```json
{
  id:236,
  cameraId:23,
  timestamp:1553774407040
}
``` 


### alert

Schema

```json
{
  id:{
    type:"int",
    description:"id"
  },
  categories:{
    type:"string[]",
    description:"list of categories"
  },
  zones:{
    type:"string[]",
    description:"list of zones"
  },
  level:{
    type:"string",
    description:"alert level"
  },
  notes:{
    type:"string",
    description:"notes"
  },
  from:{
    type:"timestamp",
    description:"alert starting time"
  },
  to:{
    type:"timestamp",
    description:"alert end time"
  }
}
``` 

Example 

```json
{
  id:10,
  categories:[
    "C1",
    "C2",
    "C3"
  ],
  zones:[
    1,
    2,
    3
  ],
  level:"Livello ...",
  notes:"Note ...",
  from:1556697241089,
  to:1556697261089
}
``` 