# Star Chart

If you're looking to quickly integrate this feature on your website without making API calls, checkout [Widgets](https://docs.astronomyapi.com/widgets)

## Generate star chart

<mark style="color:green;">`POST`</mark> `https://api.astronomyapi.com/api/v2/studio/star-chart`

#### Headers

| Name                                            | Type   | Description   |
| ----------------------------------------------- | ------ | ------------- |
| Authorization<mark style="color:red;">\*</mark> | string | Basic \<hash> |

#### Request Body

| Name                                       | Type   | Description                                                                                                                                                                     |
| ------------------------------------------ | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| style                                      | string | Style of the map to be generated. If not provided will use the default style. To see a demo of available styles see styles section on this page.                                |
| observer<mark style="color:red;">\*</mark> | object | Observer object must contain the `latitude`, `longitude` and `date` of the observer.                                                                                            |
| view<mark style="color:red;">\*</mark>     | object | View object is used to configure the view of the rendered image. The view object must contain a `type` and `parameters` object. Parameters object can vary based on the `type`. |

{% tabs %}
{% tab title="200: OK " %}

```typescript
{
 "data": {
     "imageUrl": "https://widgets.astronomyapi.com/star-chart/generated/1234567890.png"
  }
}
```

{% endtab %}
{% endtabs %}

### Rendering different views

#### Constellation

To generate an image of a constellation the `type` in the `view` object must be set to `constellation`. The 3 letter ID of the constellation must be passed in the parameters for the view object. For a complete list of constellation IDs see [Contellation Enums](https://docs.astronomyapi.com/requests-and-response/constellation-enums)

{% hint style="info" %}
The 3 letter constellation ID is case sensitive, only lower case is allowed
{% endhint %}

```typescript
{
    "style": "inverted",
    "observer": {
        "latitude": 33.775867,
        "longitude": -84.39733,
        "date": "2019-12-20"
    },
    "view": {
        "type": "constellation",
        "parameters": {
            "constellation": "ori" // 3 letter constellation id
        }
    }
}
```

#### Area

To generate an image of an area in the sky, set the `type` to `area`, then pass the RA and Dec values in the `position` object for the view `parameters`. Currently equatorial coordinates are supported by the API. Additionally the parameter `zoom` can be provided to scale the image, but it's optional.

```typescript
// Note how this request does not have the field `style` 
// The API will use the default style
{
    "observer": {
        "latitude": 33.775867,
        "longitude": -84.39733,
        "date": "2019-12-20"
    },
    "view": {
        "type": "area",
        "parameters": {
            "position": {
                "equatorial": {
                    "rightAscension": 14.83,
                    "declination": -15.23
                }
            },
            "zoom": 3 //optional
        }
    }
}
```

## Styles

### `default`

![](https://1238588302-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MKQ7_I-c79Ln1c6Chop%2F-MKW2xsB1FIz_bfFm8UD%2F-MKW5jl6n9ePkwbwSgZa%2Fa458456e6535de44ec8cf5fc78e54230efd961319d1e04615235585de53a4c98.png?alt=media\&token=c6a963cc-cebe-4f10-8f51-4e8c588ff8bc)

### `inverted`

![](https://1238588302-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MKQ7_I-c79Ln1c6Chop%2F-MKW2xsB1FIz_bfFm8UD%2F-MKW5w2ZZTYQJUZv1oWf%2Fd11505ad53287e9bbb36be2f059b09fa3e0b765408e2df6659bb8e37957668db.png?alt=media\&token=fbb0f292-1649-4935-9fb4-c4132407be0e)

### `navy`

![](https://1238588302-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MKQ7_I-c79Ln1c6Chop%2F-MKciiD19Q46fwe02Bln%2F-MKckhK5zU1qi2fDAHqX%2Fb7654698395061f2e6985b49c5f9b4e6a55c5aec350f9919a3e00818c701d199.png?alt=media\&token=23842538-af4f-4628-b42d-bff2c6a3c7a1)

### `red`

![](https://1238588302-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MKQ7_I-c79Ln1c6Chop%2F-MKciiD19Q46fwe02Bln%2F-MKckWpuoGMwb66NMaPE%2F9094a7b39b3ff6b06cf577ceb8f4c1cac3d2aa25fd07c74cb23f109ff32f5f59.png?alt=media\&token=bf472a14-f152-44c5-bb5a-fcf451851089)
