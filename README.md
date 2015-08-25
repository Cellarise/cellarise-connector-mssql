# cellarise-connector-mssql
[![view on npm](http://img.shields.io/npm/v/cellarise-connector-mssql.svg?style=flat)](https://www.npmjs.org/package/cellarise-connector-mssql)
[![npm module downloads per month](http://img.shields.io/npm/dm/cellarise-connector-mssql.svg?style=flat)](https://www.npmjs.org/package/cellarise-connector-mssql)
[![Dependency status](https://david-dm.org/Cellarise/cellarise-connector-mssql.svg?style=flat)](https://david-dm.org/Cellarise/cellarise-connector-mssql)
[![Build Status](https://travis-ci.org/Cellarise/cellarise-connector-mssql.svg?branch=master)](https://travis-ci.org/Cellarise/cellarise-connector-mssql)
[![Code
Climate](https://codeclimate.com/github/Cellarise/cellarise-connector-mssql/badges/gpa.svg)](https://codeclimate.com/github/Cellarise/cellarise-connector-mssql)
[![Test Coverage](https://codeclimate.com/github/Cellarise/cellarise-connector-mssql/badges/coverage.svg)](https://codeclimate.com/github/Cellarise/cellarise-connector-mssql/badges/coverage.svg)

> MsSQL adapter for Loopback


##Installation

Install `cellarise-connector-mssql`:
```
npm install -g cellarise-connector-mssql
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




## API
*documented by [jsdoc-to-markdown](https://github.com/75lb/jsdoc-to-markdown)*.


# Changelog

<table style="width:100%;border-spacing:0px;border-collapse:collapse;margin:0px;padding:0px;border-width:0px;">
  <tr>
    <th style="width:20px;text-align:center;"></th>
    <th style="width:80px;text-align:center;">Type</th>
    <th style="width:80px;text-align:left;">ID</th>
    <th style="text-align:left;">Summary</th>
  </tr>
    
<tr>
        <td colspan=4><strong>Version: 0.1.0 - released 2015-08-25</strong></td>
      </tr>
        
<tr>
            <td style="width:20px;padding:0;margin:0;text-align:center;"><img src="https://jira.cellarise.com:80/secure/viewavatar?size=xsmall&amp;avatarId=10419&amp;avatarType=issuetype"/></td>
            <td style="width:80px;text-align:left;">Non-functional</td>
            <td style="width:80px;text-align:left;">MDCNSQL-5</td>
            <td><p>Package: Update development dependencies</p><p></p></td>
          </tr>
        
<tr>
            <td style="width:20px;padding:0;margin:0;text-align:center;"><img src="https://jira.cellarise.com:80/secure/viewavatar?size=xsmall&amp;avatarId=10412&amp;avatarType=issuetype"/></td>
            <td style="width:80px;text-align:left;">Minor</td>
            <td style="width:80px;text-align:left;">MDCNSQL-4</td>
            <td><p>Package: update based on changes to loopback-connector</p><p></p></td>
          </tr>
        
<tr>
            <td style="width:20px;padding:0;margin:0;text-align:center;"><img src="https://jira.cellarise.com:80/secure/viewavatar?size=xsmall&amp;avatarId=10411&amp;avatarType=issuetype"/></td>
            <td style="width:80px;text-align:left;">Feature</td>
            <td style="width:80px;text-align:left;">MDCNSQL-3</td>
            <td><p>Include: Add SQL LEFT OUTER JOIN option for includes</p><p></p></td>
          </tr>
        
<tr>
            <td style="width:20px;padding:0;margin:0;text-align:center;"><img src="https://jira.cellarise.com:80/secure/viewavatar?size=xsmall&amp;avatarId=10411&amp;avatarType=issuetype"/></td>
            <td style="width:80px;text-align:left;">Feature</td>
            <td style="width:80px;text-align:left;">MDCNSQL-2</td>
            <td><p>Package: Add mssql connector for loopback-datasource-juggler</p><p></p></td>
          </tr>
        
    
</table>



# License

MIT. All rights not explicitly granted in the license are reserved.

Copyright (c) 2015 Cellarise
## Dependencies
[cellarise-connector-mssql@0.0.0](&quot;https://github.com/Cellarise/cellarise-connector-mssql&quot;) - &quot;MIT&quot;, 
*documented by [npm-licenses](http://github.com/AceMetrix/npm-license.git)*.
