# Chromium Host
A .NET/Mono Chromium Embedded Framework host

![](https://github.com/kagaconnect/chromium_host/blob/master/assets/svgs/release.svg) ![](https://github.com/kagaconnect/chromium_host/blob/master/assets/svgs/linux.svg) ![](https://github.com/kagaconnect/chromium_host/blob/master/assets/svgs/windows.svg)

### Features
- Database Clients : Can call MS SQL Server, MySQL Server and SqLite databases.
- .Net Framework : eposes functions from the mscorlib, System and System.Core libraries
- Window : exposes chromium embedded framework browser functions.
- Console : extends some logging functionality
- Server : a simple http server
- Stream : eposes a network stream client or serial stream client

### Examples - Database clients
```javascript
function SqlConnection(host, user, pass){
  if(DB != undefined && DB != null){
    return DB.connection(host, user, pass, "sql");
  }
  return null;
}

function MySqlConnection(host, user, pass){
  if(DB != undefined && DB != null){
    return DB.connection(host, user, pass, "mysql");
  }
  return null;
}

function SqlLiteConnection(host, user, pass){
  if(DB != undefined && DB != null){
    return DB.connection(host, user, pass, "sqlite");
  }
  return null;
}
	
//Asynchronous
var con = new app.db.MySqlConnection("127.0.0.1;Port=3306","root","test123$");
if(con != null){
	con.open();
	con.changeDatabase("fake_database");
	
	var cmd = con.createCommand("Selet * from fake_table where `fake_column` = @fake_colun");
	if(cmd != null){
		cmd.addParameter("@fake_colun", "Text", "bla bla bla");
		
		var reader = comm.executeReader(function(readerID){
			if(reader != null){
				var _close = function(){
					reader.close();
					con.close();
					
					console.log("completed");
				};
				
				var _loopBack = function(){
					var row = JSON.parse(reader.getValues());
					console.log(row);
					
					if(reader.read())setTimeout(_loopBack,1);
					else _close();
				};
				
				if(reader.read())setTimeout(_loopBack,1);
				else _close();
			});
		}
		else con.Close();
	}
	else con.close();
}

//synchronize
var con = new app.db.SqlConnection("127.0.0.1,1433","root","test123$");
if(con != null){
	con.open();
	con.changeDatabase("fake_database");
	
	var cmd = con.createCommand("Selet * from fake_table where `fake_column` = @fake_colun");
	if(cmd != null){
		cmd.addParameter("@fake_colun", "Text", "bla bla bla");
		
		var reader = comm.executeReader();
		if(reader != null){
			while(reader.read()){
				var row = JSON.parse(reader.getValues());
				console.log(row);
			}
		}
		else reader.close();
		con.close();
	}
	else con.close();
}
```

### Dependents
- [CefGlue](https://gitlab.com/xiliumhq/chromiumembedded/cefglue)
- [ICSharpCode.SharpZipLib](https://github.com/icsharpcode/SharpZipLib)
- [NetCoreEx](https://github.com/prasannavl/NetCoreEx)
- [SerialPortStream](https://github.com/jcurl/SerialPortStream)
- [Mono framework on linux](https://www.mono-project.com/)
- [.Net framework on windows](https://www.microsoft.com/en-us/download/details.aspx?id=49981)
- [WinApi](https://github.com/prasannavl/WinApi)
- [Mysql](https://www.mysql.com/)
- freedesktop binding
