# Set Data in Provider

TODO: update this

Add the following code to the update method of the provider file.

```
    context.notice("Setting '#{name}' with #{should.inspect}")
    context.notice('running the setter')
    url = URI('https://firebase-apiserver20-tah01-iad01.dapi.production.nest.com:9553') # eyaml

    http = Net::HTTP.new(url.host, url.port)
    http.use_ssl = true
    http.verify_mode = OpenSSL::SSL::VERIFY_NONE

    request = Net::HTTP::Put.new(url)
    request['authorization'] = '<your unique id>'
    request['content-type'] = 'application/json'
    request.body = '{target_temperature_c:}'

    response = http.request(request)

    context.notice(response.code)
    context.notice(JSON.parse(response.body))
    JSON.parse(response.body)
```

Run ```pdk validate```.

Add tests, run ```pdk test unit```

Deploy the code again: cp -R

Now that we've done all that we'll create a manifest to apply some data. This will set the temperature of the thermostat.

[15. Create Manifest](../15-create-manifest)
