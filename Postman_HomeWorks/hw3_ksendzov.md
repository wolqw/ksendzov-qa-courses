```javascript
> 1 stage
var gr_34_json = pm.response.json();
var gr_34_token = gr_34_json.token
pm.environment.set("auth_token", gr_34_token);
