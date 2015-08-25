##Installation

Install `{name}`:
```
npm install -g {name}
```


##Usage

This package uses the [mssql](//github.com/patriksimek/node-mssql) package which in turn uses [tedious](//github.com/pekim/tedious) out of the box. Support is also provided for the native Windows MSSQL driver as well as node-tds. See the mssql documentation page for more information.

1. Setup dependencies in package.json:
  <pre>
    <code>
    {
      ...
      "dependencies":{
		    "loopback": "^2.18.0",
		    "loopback-datasource-juggler": "^2.29.2",
      }
      ...
    }
    </code>
  </pre>
2. Use:
  <pre>
    <code>
    var Schema = require("jugglingdb").Schema;
    var schema = new Schema("mssql", {host:"YourSqlServer", database:"YourDatabase"});
    ...
    </code>
  </pre>
  <pre>
    <code>
    var Schema = require("jugglingdb").Schema;
    var schema = new Schema("mssql", {host:"AzureServer", database:"YourDatabase",
                                      username: "YourUserName", password: "YourPassword",
                                      azure: true});
    ...
    </code>
  </pre>
3. Primary Keys:
  using anything other than the default 'id' as the primary key
  will cause the hasMany and belongsTo relationships in jugglingdb to
  not work, and possibly other oddities as well (so you probably
  shouldn't use it until it's officially supported).

  to specify a custom primary key name for a model use
  <pre>
    <code>
      var AppliesTo = schema.define("AppliesTo", {
        AppliesToID: {
          type:Number,
          primaryKey:true
        },
        Title: {
          type:String,
          limit:100
        },
        Identifier: {
          type:String,
          limit:100
        },
        Editable: {
          type:Number
        }
      });
    </code>
  </pre>

