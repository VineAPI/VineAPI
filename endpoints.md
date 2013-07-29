# Users


## Authentication

### Signup

`POST - /users`

Data
* `username`
* `password`: *must contain a number*
* `email`
* `authenticate`: 1

### Login

`POST - /users/authenticate`

Data
* `username` *email address*
* `password`
* `[deviceToken]`

### Logout

`DELETE - /users/authenticate`


## Profile

### Self profile

`GET - /users/me`

### User profile

`GET - /users/profiles/<userId>`

### Update profile

`PUT - /users/<userId>`

Data

* `description`
* `location`
* `locale` - 2 char locale (used for phone number)
* `private` - 0|1
* `phoneNumber`

### Set sensitive profile

`POST - /users/<userId>/explicit`

### Unset sensitive profile

`DELETE - /users/<userId>/explicit`


## Actions

### Follow

`POST - /users/<userId>/followers`

### Unfollow

`DELETE - /users/<userId>/followers`

### Block

`POST - /users/<userId>/blocked/<userIdToBlock>`

### Unblock

`DELETE - /users/<userId>/blocked/<userIdToBlock>`

### Get pending notifications count

`GET - /users/<userId>/pendingNotificationsCount`

### Get notifications

`GET - /users/<userId>/notifications`



## Lists

### Followers

`GET - /users/<userId>/followers`

### Following

`GET - /users/<userId>/following`


# Posts

## Actions

### Like

`POST - /posts/<postId>/likes`

### Unlike

`DELETE - /posts/<postId>/likes`

### Comment

`POST - /posts/<postId>/comments`

Data

* `comment`
* `entities` - TO DO
  + [{'type': 'mention','id': <userId>,'text': <username>,'range': '[start,end]'}] 
  + [{'type': 'mention','id': '972994914382217210','text': 'Test','range': '[5,9]'}]

### Uncomment

`DELETE - /posts/<postId>/comments/<commentId>`

### Revine

`POST - /posts/<postId>/repost`

### Unrevine

`DELETE - /posts/<postId>/repost/<revineId>`

### Report

`POST - /posts/<postId>/complaints`

## Management

### Create post

`POST - /posts`

Data

* `videoUrl`
* `thumbnailUrl`
* `description`
* `entities`
* `[forsquareVenueId]`
* `[venueName]`
* `[channelId]`

### Delete post

`DELETE - /posts/<postId>`



# Timelines

Params

* `page`
* `size`
* `anchor`

### Single post

`GET - /timelines/posts/<postId>`

### User timeline

`GET - /timelines/users/<userId>`

### User likes

`GET - /timelines/users/<userId>/likes`

### Tag timeline

`GET - /timelines/tags/<tagName>`

### Main timeline

`GET - /timelines/graph`

### Popular timeline

`GET - /timelines/popular`

### On The Rise timeline

`GET - /timelines/trending`

### Editors Pick timeline

`GET - /timelines/promoted`

### Channel popular timeline

`GET - /timelines/channels/<chanelId>/popular`

### Channel recent timeline

`GET - /timelines/channels/<chanelId>/recent`

### Venue timeline

`GET - /timelines/venues/<venueId>`



# Tags

### Trending

`GET - /tags/trending`



# Channels

### Featured

`GET - /channels/featured`



# Search

### Users

`GET - /users/search/<query>`

### Tags

`GET - /tags/search/<tagName>`

Params

* `page`
* `size`
* `anchor`



# Media

### Upload thumbnail

`PUT - https://media.vineapp.com/upload/thumbs/1.3.1.mp4.jpg`

```
Host:              media.vineapp.com
Proxy-Connection:  keep-alive
Content-Type:      image/jpeg
X-Vine-Client:     ios/1.3.1
Content-Length:    20486
Accept-Language:   en;q=1, fr;q=0.9, de;q=0.8, ja;q=0.7, nl;q=0.6, it;q=0.5
Accept:            */*
vine-session-id:   key
Accept-Encoding:   gzip, deflate
Connection:        keep-alive
User-Agent:        iphone/1.3.1 (iPad; iOS 6.1.3; Scale/1.00)
JPEG image
Format           JPEG (ISO 10918)
Size             480 x 480 px
Mode             RGB
jfif             257
jfif_density     (1, 1)
jfif_unit        0
jfif_version     (1, 1)
Orientation      1
ExifOffset       38
ColorSpace       1
ExifImageWidth   480
ExifImageHeight  480

+

Image?
```

Response

```
Content-Type:    application/json
Date:            Sun, 28 Jul 2013 07:22:01 GMT
Server:          nginx/1.4.1
X-Upload-Key:    https://vines.s3.amazonaws.com/thumbs_trellis/2013/07/28/C312D449AE973170415491244032_1.3.1.mp4_z24oHhUPAjIZEOmF_g3cEJ3faB0sOcV5aulnD5JF6LuFHqndOncAK9hd2GbEqAuB.jpg
Content-Length:  0
Connection:      keep-alive
```


### Upload video

`PUT - https://media.vineapp.com/upload/videos/1.3.1.mp4`

```
Host:              media.vineapp.com
Proxy-Connection:  keep-alive
Content-Type:      video/mp4
X-Vine-Client:     ios/1.3.1
Content-Length:    312112
Accept-Language:   en;q=1, fr;q=0.9, de;q=0.8, ja;q=0.7, nl;q=0.6, it;q=0.5
Accept:            */*
vine-session-id:   key
Accept-Encoding:   gzip, deflate
Connection:        keep-alive
User-Agent:        iphone/1.3.1 (iPad; iOS 6.1.3; Scale/1.00)
+
RAW video
```

Reponse

```
Content-Type:    application/json
Date:            Sun, 28 Jul 2013 07:22:01 GMT
Server:          nginx/1.4.1
X-Upload-Key:    https://vines.s3.amazonaws.com/videos_trellis/2013/07/28/00E889E438973170413238661120_1.3.1_kV7ug1Uwie53xiSVgod_otyF1vkyN2iQghPjddNLWLjW5EwTeiL_d7GUNY_WdPOA.mp4
Content-Length:  0
Connection:      keep-alive
```

### Upload avatar

`PUT - https://media.vineapp.com/upload/avatars/1.3.1.jpg`

```
Host: media.vineapp.com
Proxy-Connection: keep-alive
Content-Type: image/jpeg
X-Vine-Client: ios/1.3.1
Content-Length: 47412
Accept-Language: en;q=1, fr;q=0.9, de;q=0.8, ja;q=0.7, nl;q=0.6, it;q=0.5
Accept: */*
vine-session-id: key
Accept-Encoding: gzip, deflate
Connection: keep-alive
User-Agent: iphone/1.3.1 (iPad; iOS 6.1.3; Scale/1.00)
<FILE>
```
