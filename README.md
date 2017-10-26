# Youtube Stream Analytics

A small Sinatra application to show relevant analytics/metrics for
YouTube livestreams in collaboration with Vox Product Team and Polygon. 

[Vox Blog](https://product.voxmedia.com/2017/8/10/16115358/doing-it-live-lessons-from-vox-products-2017-summer-interns?utm_campaign=product.voxmedia&utm_content=chorus&utm_medium=social&utm_source=twitter)
![alt text](https://i.imgur.com/32XmZMd.png "screenshot")

### Development

Run the following commands to boot the application. This assumes you
already have Docker installed on the host computer. Make sure you have
an `.env` file with `YOUTUBE_API_KEY` defined -- see `.env.example` for
an example of how to do this.

```bash
docker build -t youtube-stream-analytics .
docker run -p 3000:3000 youtube-stream-analytics
```
### Accessing the Live-chat Data

Open up ruby console using ` irb ` 
then ` require 'rest-client' `

Go to youtube and find the id of the live data you wish to view the live chat stream from. 
Example: watch?v=pi8bY8ncaRY
The ID is everything after v= 

on the console type 
``` RestClient.post('localhost:3000/video', { id: 'insert-id-from-live-video' }) ```
Copy the "live-chat-id" and paste on your browser the following with your live chat id

``` http://localhost:3000/analytics?live_chat_id=paste-here ```

# Contributors

* Bernard Decelian
* Jon Moss
* Leslie Manrique
* Michael Martinez
* Nasita Haque
 