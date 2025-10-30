# Events

Events API can return events for a single body for the given date range. In the events API currently, only the bodies `Sun` and `Moon` are supported.

See [Event Properties](https://docs.astronomyapi.com/requests-and-response/event-properties) for available event properties for bodies.

## Get events for the given body

<mark style="color:blue;">`GET`</mark> `https://api.astronomyapi.com/api/v2/bodies/events/:body`

Returns events for the given body for the given date range in tabular format.

#### Path Parameters

| Name                                   | Type   | Description    |
| -------------------------------------- | ------ | -------------- |
| body<mark style="color:red;">\*</mark> | string | ID of the body |

#### Query Parameters

| Name                                         | Type   | Description                                                                                                                 |
| -------------------------------------------- | ------ | --------------------------------------------------------------------------------------------------------------------------- |
| latitude<mark style="color:red;">\*</mark>   | string | Latitude of the observer's location                                                                                         |
| longitude<mark style="color:red;">\*</mark>  | string | Longitude of the observer's location                                                                                        |
| elevation<mark style="color:red;">\*</mark>  | string | Elevation from the sea in Meters                                                                                            |
| from\_date<mark style="color:red;">\*</mark> | string | Starting date as Date. The maximum number of days you can query is 366 days.                                                |
| to\_date<mark style="color:red;">\*</mark>   | string | Ending date as Date. The maximum number of days you can query is 366 days.                                                  |
| time<mark style="color:red;">\*</mark>       | string | Observer's time as Time                                                                                                     |
| output                                       | string | <p>Output format.</p><p><code>rows</code></p><p>or</p><p><code>table</code></p><p>. Default is</p><p><code>table</code></p> |

#### Headers

| Name                                            | Type   | Description |
| ----------------------------------------------- | ------ | ----------- |
| Authorization<mark style="color:red;">\*</mark> | string | Basic       |

{% tabs %}
{% tab title="200: OK Response for a request made with " %}

```javascript
{
    "data": {
        "dates": {
            "from": "2020-12-20T09:00:00.000-05:00",
            "to": "2021-12-23T09:00:00.000-05:00"
        },
        "observer": {
            "location": {
                "longitude": -84.39733,
                "latitude": 38.775867,
                "elevation": 0
            }
        },
        "rows": [
            {
                "body": {
                    "id": "sun",
                    "name": "Sun"
                },
                "events": [
                    {
                        "type": "partial_solar_eclipse",
                        "eventHighlights": {
                            "partialStart": {
                                "date": "2021-06-10T03:45:15.241-05:00",
                                "altitude": -13.56
                            },
                            "totalStart": null,
                            "peak": {
                                "date": "2021-06-10T04:37:30.267-05:00",
                                "altitude": -5.85
                            },
                            "totalEnd": null,
                            "patialEnd": {
                                "date": "2021-06-10T05:32:52.677-05:00",
                                "altitude": 2.92
                            }
                        },
                        "rise": "2021-06-10T10:12:14.143Z",
                        "set": "2021-06-11T01:02:13.766Z",
                        "extraInfo": {
                            "obscuration": 0.76
                        }
                    }
                ]
            }
        ]
    }
}
```

{% endtab %}
{% endtabs %}
