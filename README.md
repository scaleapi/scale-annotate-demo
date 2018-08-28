Scale Annotation Demo
====
![alt text](http://i.imgur.com/OUFQvBg.png "Demo Screenshot")
This app demonstrates what [Scale API's](https://www.scaleapi.com) [annotation endpoint (bounding box)](https://blog.scaleapi.com/introducing-our-bounding-box-endpoint-7f2b1d07f7a7) can do.

You can deploy it to Heroku yourself following the instructions below, and feel free to build on top of it to build your own image recognition applications.

Discuss it with us on Scale's Slack channel!

[<img src="http://scalesupport.herokuapp.com/badge.svg">](https://scalesupport.herokuapp.com)

## deploy on heroku
1. create an [S3 bucket](https://docs.aws.amazon.com/AmazonS3/latest/gsg/CreatingABucket.html)
2. get [Google ReCaptcha keys](https://www.google.com/recaptcha/admin#list)
3. get [Scale API keys](https://www.scaleapi.com)
4. [![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

## run locally
1. create/get all keys mentioned above
2. `git clone https://github.com/scaleapi/scale-annotate-demo`
3. `cd scale-annotate-demo`
4. `bundle install`
5. `rake db:migrate`
6. set environment variables as specified in [secrets.yml](config/secrets.yml) possibly with [dotenv](https://github.com/bkeepers/dotenv)
7. `rails s`

## structure
### rails backend
- [AnnotationRequestsController](app/controllers/api/annotation_requests_controller.rb) - handles API calls for the showing and creation of annotation requests
- [CallbackController](app/controllers/callback_controller.rb) - handles Scale's callback
- [ScaleHelper](app/helpers/scale_helper.rb) - sends Scale API calls
- [models](app/models) - application models
- [migrations](db/migrate) - model migrations

### angular frontend
- [application.js.erb](app/assets/javascripts/application.js.erb) - main angular js
- [templates](app/assets/javascripts/templates) - angular templates
