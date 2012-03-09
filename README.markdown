# gae-rest-webapp

This lib can be used to expose your Google App Engine Datastore models vi an easy-to-use JSON REST API.

All you need to do is plug in your models, and it will build a Route object for webapp2 for you. It will even inspect an entire module for models, and include them all.

*An example that imports all models from the "mymodels" module, and exposes them via an API*

```python
    import mymodels, webapp2, REST
    
    application = webapp2.WSGIApplication([
        # your app's other routes can go here
        REST.BuildRoute("/api", mymodels)
    ],debug=True)
```

*Or just list specific models*

```python
    import mymodels, webapp2, REST
    
    application = webapp2.WSGIApplication([
        # your app's other routes can go here
        REST.BuildRoute("/api", [mymodels.Foo, mymodels.Bar, mymodels.Baz])
    ],debug=True)
```
