# Moon Phase

If you're looking to quickly integrate this feature on your website without making API calls, checkout [Widgets](https://docs.astronomyapi.com/widgets)

## Generate Moon Phase

<mark style="color:green;">`POST`</mark> `https://api.astronomyapi.com/api/v2/studio/moon-phase`

#### Headers

| Name                                            | Type   | Description   |
| ----------------------------------------------- | ------ | ------------- |
| Authorization<mark style="color:red;">\*</mark> | string | Basic \<hash> |

#### Request Body

| Name                                       | Type   | Description                                                                                                                                                                                                                                                                                                                                                                |
| ------------------------------------------ | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| format                                     | string | Image format to be returned. Valid values are `png` or `svg`. Defaults to `png`                                                                                                                                                                                                                                                                                            |
| style                                      | object | Style object contains the styling parameters for the image generated.                                                                                                                                                                                                                                                                                                      |
| observer<mark style="color:red;">\*</mark> | object | Observer object must contain the `latitude`, `longitude` and `date` of the observer.                                                                                                                                                                                                                                                                                       |
| view<mark style="color:red;">\*</mark>     | object | <p>View object is used to configure the view of the rendered image. The view object must contain a <code>type</code> object. </p><p></p><p><code>orientation</code> specifies which side of the moon should be up depending on the hemisphere you live in the world. This parameter is optional. If not provided AstronomyAPI will determine the values automatically.</p> |

{% tabs %}
{% tab title="200: OK " %}

```typescript
{
    "data": {
        "imageUrl": "https://widgets.astronomyapi.com/moon-phase/generated/1234567890.png"
    }
}
```

{% endtab %}
{% endtabs %}

```typescript
{
    "format": "png",
    "style": {
        "moonStyle": "sketch",
        "backgroundStyle": "stars",
        "backgroundColor": "red",
        "headingColor": "white",
        "textColor": "red"
    },
    "observer": {
        "latitude": 6.56774,
        "longitude": 79.88956,
        "date": "2020-11-01"
    },
    "view": {
        "type": "portrait-simple",
        "orientation": "south-up"
    }
}
```

## Format

The API currently supports outputting images in `svg` and `png` formats. These can be used in different use cases, depending on how and where you want them to be displayed.&#x20;

## Style

#### `moonStyle`

Valid values are `default`, `sketch` and `shaded.` Below are sample moons for each value.

<div align="left"><img src="https://1238588302-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MKQ7_I-c79Ln1c6Chop%2F-MLMcIv7WeAS5ac0ZVnC%2F-MLMfuVXwb-nvqU5Gd3F%2Fmoon.285d.png?alt=media&#x26;token=93c058ab-4d2a-462e-9bf4-4647c532448a" alt="default"></div>

<div align="left"><img src="https://1238588302-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MKQ7_I-c79Ln1c6Chop%2F-MLMcIv7WeAS5ac0ZVnC%2F-MLMfxkLOrFj75Y6WLqR%2Fmoon.285s.png?alt=media&#x26;token=23d259c6-acd9-4721-9e34-9da3f0a011af" alt="shaded"></div>

<div align="left"><img src="https://1238588302-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MKQ7_I-c79Ln1c6Chop%2F-MLMcIv7WeAS5ac0ZVnC%2F-MLMg2GgWznHGk4LErJE%2Fmoon.285k.png?alt=media&#x26;token=99b9e115-c271-4681-93ff-7d3244887585" alt="sketch"></div>

#### `backgroundStyle`

Background style supports the values either `stars` or `solid`. Passing `stars` will render a stars background while `solid` will render the background with a solid color specified by the `backgroundColor` property.

#### `backgroundColor, headingColor and textColor`

These properties could be used to customise the image further. Colours could be defined as hex or as any of the [140 html colour names](https://www.w3schools.com/tags/ref_colornames.asp).

## View

#### `type`

The type parameter in the view object should specify which template to be used when rendering the image. Currently two templates are available.

<div align="left"><img src="https://1238588302-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MKQ7_I-c79Ln1c6Chop%2F-MLMiqEcj7xvMBhQb-0l%2F-MLMjeSRNBAehVN5Cx6W%2Fe86043757e0a337db6d529d42e6c67e9e832b104f75d92bf9e6a09fc4d44cc25.png?alt=media&#x26;token=9dc03712-bb81-401d-85d9-da8d14e56411" alt="portrait-simple"></div>

<div align="left"><img src="https://1238588302-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MKQ7_I-c79Ln1c6Chop%2F-MLMiqEcj7xvMBhQb-0l%2F-MLMjiu-yLVApMbCY5pg%2Ff2968861e774a453f7826a48bb0c1f41c22693a3b58475cbec0435e97171d8e2.png?alt=media&#x26;token=289c3cfd-2bb1-452c-8b40-819508dee67d" alt="landscape-simple"></div>

#### `orientation`

Orientation parameter in the view object, determines which orientation to use when rendering the moon. By default it will render north side up, as seen by an observer facing the south side of the sky. This parameter is optional.

Below is an example of the same image with different orientations.

<div align="left"><img src="https://1238588302-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MKQ7_I-c79Ln1c6Chop-3789850253%2Fuploads%2FnRuOUVH6sAwH6qTSqPGg%2F33574d6b80418fce7f3cb4ba97e09ea0f460f7780b6a3367dda5e58643896230.png?alt=media&#x26;token=f3a7d6c8-1a3e-4a18-beea-f81120972159" alt="north-up"></div>

<div align="left"><img src="https://1238588302-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MKQ7_I-c79Ln1c6Chop-3789850253%2Fuploads%2FCWePAkuVykisjwBTPzPh%2F0b12c46d2b33d72b4f848cd40d878221e57689ab2880d104d615721912dd5593.png?alt=media&#x26;token=a66bb864-9c6a-434f-8b50-8e876fc65b04" alt="south-up"></div>
