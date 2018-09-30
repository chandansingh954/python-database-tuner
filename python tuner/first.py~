import mysql.connector as mariadb

db=mariadb.connect(host='localhost',database='tuner',user='root',password='avinash')
cursor = db.cursor()
# print " Hello world" this code is print only once when it is import in main.py and method is called in main.py

# now in every method we write query and then execute it and if get the data the call the method fetchone(),fetchall(),rowcount()
# In java or python no nedd to execute query use tuner from java or python
def forShowDatabases():
	try:
		sql ="show databases"
		cursor.execute(sql)
		databases =cursor.fetchall()
		databaseList=[]
		for database in databases:
			s = database[0] 	
			b=s.encode('ascii')
			databaseList.append(b)
		return databaseList
	except:
		print " Failed to show database"

def showDatabases():
	try:
		sql ="show databases"
		cursor.execute(sql)
		databases =cursor.fetchall()
		for database in databases:
			s = database[0] 	
			b=s.encode('ascii')
			print b
	except:
		print " Failed to show database"

def createDatabase(name):
	try:
		sql ="create database "+name
		cursor.execute(sql)
		print "Successfully database will be created "
	except:
		print " Failed to create database"

def useDatabase(name):	
	try:
		sql ="use "+name
		cursor.execute(sql)
		print "Successfully database selected "
	except:
		print " Failed to change the database"


def checkDatabase():
	try:
		sql ="select database() " 
		cursor.execute(sql)
		database = cursor.fetchone()# database is tuple
		print "Database version  = ",database[0].encode('ascii')
	except:
		print " Failed to show the selected database  "
def forGetTableChoice():
	try:
		cursor.execute("show tables")
		tables = cursor.fetchall()
		tableList=[]
		for table in tables:	
			b=table[0].encode('ascii')
			tableList.append(b)
		return tableList
	except:
		print "Failed to get the tables"
 
def showtables():
	try:
		cursor.execute("show tables")
		tables = cursor.fetchall()
		for table in tables:
			s = table[0] 	
			b=s.encode('ascii')
			print b
	except:
		print "Failed to show the tables"

def describeTable(tableName):
	try:
		sql = "describe "+tableName		
		cursor.execute(sql)
		datas = cursor.fetchall()
		for data in datas: 
				
			print " Field : "+data[0].encode('ascii'),
			print " Type : "+data[1].encode('ascii'),
			print " Null : "+data[2].encode('ascii'),
			print " Key : "+data[3].encode('ascii'),
			#print "Default :"+data[4],
			print " Extra : "+data[5].encode('ascii')
			
	except:
		print "Failed to describe the table"

def createNewTable(lsfinal,tableName):
	try:
		sql = "create table "+tableName+"("
		for ls in lsfinal:
			for l in ls:
				sql=sql+" "+l
			sql =sql+" ,"
		sql =sql[:-1]
		sql =sql+")"
		cursor.execute(sql)	
		print " Table has been created successfully"
	except:
		print " Table is not created successfully "

def createNewTableFromExsisting(oldtable, newtable):
	try: 	
		sql = "create table if not exists "+newtable+" as select * from "+oldtable
		print sql
		cursor.execute(sql)
		print " New exsisting table has been created "
	except:
		print " Failed to create new exsisting table"

def renametable(oldname, newname):
	try:
		sql ="rename table "+oldname+" to "+newname
		cursor.execute(sql)
		print " Successfylly change the name "
	except:
		print " Failed to rename the table name "

def droptable(tablename):
	try:
		sql ="drop table "+tablename
		cursor.execute(sql)
		print " Successfylly drop the table "
	except:
		print " Failed to drop the table  "

def addnewColumn(name,tp,tableName):
	try:
		sql ="alter table  "+tableName+" add  "+name+" "+tp
		cursor.execute(sql)
		print " Successfylly add the column "
	except:
		print " Failed to add the column "

def removeColumn(name,tableName):
	try:
		sql ="alter table  "+tableName+" drop  "+name
		cursor.execute(sql)
		print " Successfylly remove the column "
	except:
		print " Failed to remove the column "

def changeColumnNameType(oldName,newName,tp,tableName):
	try:
		sql ="alter table  "+tableName+" change  "+oldName+"  "+newName+"  "+tp
		cursor.execute(sql)
		print " Successfylly modify the column name "
	except:
		print " Failed to modify the column name "
def forInsert(tableName):
	try:
		sql ="describe "+tableName
		cursor.execute(sql)
		datas = cursor.fetchall()
		return datas
	except:
		print "Failed to get the description of table  "

def insertRow(tableName,nameList,valueList):
	try:
		sql ="insert into "+tableName+" ("
		for n in nameList:
			sql =sql+n+","
		sql=sql[:-1]
		sql=sql+" ) values ( "
		for v in valueList:
			sql=sql+"'"+v+"'"+","
		sql=sql[:-1]
		sql=sql+" )"
		print sql
		cursor.execute(sql)
		print " Successfylly insert the data"
	except:
		print " Failed to insert the data " 

def getColumnNameTable(tableName): # this method return table field in list when we pass the table
		sql = "describe "+tableName
		cursor.execute(sql)
		datas=cursor.fetchall()
		ls=[]
		for data in datas: 				
			 ls.append(data[0].encode('ascii'))
		return ls

def getKeyFieldName(tableName):
	try:
		sql ="describe  "+tableName
		cursor.execute(sql)
		rows = cursor.fetchall()
		for row in rows:
			checkKey = row[3].encode("ascii")
			if(checkKey =="primary key"):
				value =row[0].encode("ascii")
				return value
	except:
		print " Failed to get the key field name "			

def getKeyFieldData(tableName,keyField):
	try:
		sql = "select "+keyField+" from "+tableName
		print sql		
		cursor.execute(sql)
		rows = cursor.fetchall()
		print "------"+keyField+"-------"
		for row in rows:
			for data in row:
				print data.encode("ascii")
	except:
		print " Failed to get the key field value  "


def getAllData(tableName):
	try:
		sql ="select * from  "+tableName
		print sql		
		cursor.execute(sql)
		rows = cursor.fetchall()
		print rows
		ls = getColumnNameTable(tableName)
		for l in ls:
			print l,
		for row in rows:
			for data in row:
				print data.encode('ascii'),
	except:
		print " Failed to Fetch all data"

def getSingleRowByKeyField(tableName,keyField,value):
	try:
		sql ="Select * from  "+tableName+" where "+keyField+" = "+value
		print sql
		cursor.execute(sql)
		row = cursor.fetchone()
		ls = getColumnNameTable(tableName) # it return the all field name
		for l in ls:
			print l,
		for d in row:
			print d,
	except:
		print " Failed to get the single row  "
					
		
def getSpecificColumn(tableName,lsField):
	try:
		sql ="select "
		for l in lsField:
			sql =sql+l+","
		sql =sql[:-1]
		sql=sql+"  from "+tableName;
		print sql		
		cursor.execute(sql)
		rows = cursor.fetchall()
		for p in lsField:
			print p,
		for row in rows:
			for data in row:
				print data.encode('ascii'),
	except:
		print " Failed to Fetch all data" 
# the specifier of value is string but we can choose the field as id , name  or salary . No matter in database id is integer type  and salary is #float 
def getSpecificRowByCondition(tableName,listField,sqlCondition):
	try:
		sql = "select ("
		for lField in listField:
			sql =sql+lField+","
		sql =sql[:-1]
		sql=sql+")  "+sqlCondition		
		cursor.execute(sql)
		rows = cursor.fetchall()
		for lsField1 in listField:
			print lsField1,
		for row in rows:
			for data in row:
				print data.encode('ascii'),
	except:
		print " Failed to get the row  "
def getAllColumnByMaxMin(sql,tableName):
	try:
		cursor.execute(sql)
		data = cursor.fetchone()
		field = getColumnNameTable(tableName)
		for l in field:
			print l,
		for d in data:
			print d.encode('ascii'),
	except:
		print " Failed to get the all value  "	
def getRowByInNotin(tableName,lsField,field,oper,inNotinTuple):
	try:
		sql = "select "
		for l1 in lsField:
			sql =sql+l+","
		sql=sql[:-1]
		sql= sql+" from "+tableName+" where "+field+" "+oper+inNotinTuple
		cursor.execute(sql)
		rows = cursor.fetchall()
		for l2 in lsField:
			print l,
		for row in rows:
			for d in row:
				print d.encode('ascii'),
	except:
		" Failed to get the value "
def showAggregateValue(tableName,field,func):
	try:
		sql =" select "+func+"("+field+") from "+tableName
		cursor.execute(sql)
		data = cursor.fetchone()
		print func+" "+field
		print data # Do here
	except:
		print " Failed to get the value "

	
def getNumericField(tableName):
	try:	
		sql = "describe "+tableName		
		cursor.execute(sql)
		datas = cursor.fetchall()
		lsField =[]
		for data in datas: 	
			tp = data[1].encode('ascii')
			if( (tp == "int(11)") or (tp =="int") or (tp =="float")):
				lsField.append(data[0].encode('ascii'))
		return lsField	
	except:
		print " Failed to get numeric field " 		

def updateValueInAll(tableName,field,value):
	try:
		value =int(value)
		sql = "update "+tableName+" set "+field+" = "+field+" + "+value
		cursor.execute(sql)
		print " successfully Update the value "
	except:
		print  "Failed to update the field  "


def updateValueInSpecific(tableName,updateField,updateValue,keyField,keyValue):
	try:
		sql = " Update into "+tableName+" set "
		length = len(updateField)
		i=0
		while(i<length):
			name=updateField[i]
			value=updateValue[i]
			sql=sql+name+" = "+value+","
			i=i+1
		sql=sql[:-1]
		sql=sql+"  where "+keyField+" = "+keyValue
		cursor.execute(sql)
		print " Successfully update the row  "
	except:
		print " Failed to update the row "

def delete(tableName,sqlEnd):
	try:
		sql = "Delete from  "+tableName+" where "+sqlEnd
		cursor.execute(sql)
		print " Successfully delete the row "
	except:
		print "failed to delete the row"
			


