from first import *
import sys

def getChoiceTable():
	tableList =forGetTableChoice()
	i =1	
	print "------------------------------"
	for l in tableList:
		print i," : "+l
		i=i+1
	print "------------------------------"
	choice = input(" Enter the choice  : ")
	switcher={}
	j=1
	for l1 in tableList:
		switcher[j]=l1
		j=j+1
	out= switcher.get(choice,"invalid choice ")
	return out
def getChoiceDatabase():
	dbList=forShowDatabases()
	i =1	
	print "-------------------------------"
	for l in dbList:
		print i," : "+l
		i=i+1
	print "--------------------------------"
	choice = input(" Enter the choice  : ")
	switcher={}
	j=1
	for l1 in dbList:
		switcher[j]=l1
		j=j+1
	out= switcher.get(choice,"invalid choice ")
	return out
	
def CreateDatabase():
	databaseName =raw_input(" Enter database name  :  ")
	createDatabase(databaseName)
def ShowDatabase():
	showDatabases()
def CheckDatabase():
	checkDatabase()
def UseDatabase():
	dbName = getChoiceDatabase()
	useDatabase(dbName)
def ShowTables():
	showtables()
def DescribeTable():
	tableName =getChoiceTable()
	describeTable(tableName)
			
def CreateNewTable():
	tableName = raw_input(" Enter the table name  :  ")	
	lsfinal =[]
	choice  = "yes" 
	while  (choice == "yes"):
		ls =[]	
		name = raw_input(" Enter field name  ")	
		print "---------------------------------"
		print "1 : int(11) "
		print "2 : varchar(20) "
		print "----------------------------------"
		chtype =input(" Enter your choice :  ")
		switcher={
			1:"int(11)",
			2:"varchar(20)"	
		}
		tp = switcher.get(chtype," invalid choice  ")
		print " Enter  in yes or no "
		d1 =raw_input("not null :  ")
		d2 =raw_input("auto increment :  ")
		d3 =raw_input("primary key :  ")
		ls.append(tp)
		ls.append(name)
		if(d1 == "yes"):
			ls.append("Not null")
		if(d2 == "yes"):
			ls.append("auto_increment")
		if(d3 == "yes"):
			ls.append("primary key")

		lsfinal.append(ls)
		choice = raw_input(" If u want to add further column then enter yes otherwise anyything :  ")  
			
	createNewTable(lsfinal,tableName)

def CreateNewTableFromExisting():
	oldTable=getChoiceTable()
	newTable=raw_input(" Enter the new table name  : ")
	createNewTableFromExsisting(oldTable, newTable)	

def RenameTable():
	oldname=getChoiceTable()
	newname=raw_input(" Enter the new name  : ")	
	renametable(oldname, newname)

def  DropTable():
	tablename=getChoiceTable()
	droptable(tablename)

def gettingType():
	print "---------------------------------"
	print "1 : int(11) "
	print "2 : varchar(20) "
	print  "--------------------------------"
	chtype =input(" Enter your choice :  ")
	switcher={
		1:"int(11)",
		2:"varchar(20)"	
	}
	tp = switcher.get(chtype," invalid choice  ")
	return tp	

def AddNewColumnInTable():
	tableName=getChoiceTable()
	name = raw_input(" Enter the column name  :  ")
	tp = gettingType()
	addnewColumn(name,tp,tableName)

def condField(ls):
	i=1
	print  "----------------------------"
	for l2 in ls:
		print i,": ",l2
		i=i+1
	print "-----------------------------"
	n2 = input(" Enter your choice :  ")
	j=1	
	condField={}
	for l3 in ls:
		condField[j]=l3
		j=j+1
	o2 = condField.get(n2, "Invalid choice  ")
	return o2

def  RemoveColumnInTable():
	tableName=getChoiceTable()
	lsField = getColumnNameTable(tableName)
	field=condField(lsField)
	removeColumn(field,tableName)

def   ChangeColumnNameAndType():
	tableName=getChoiceTable()
	lsField = getColumnNameTable(tableName)
	print " choose the field for change its name and type "	
	field=condField(lsField)
	newName =raw_input(field+" is old name . New name is  : " )
	tp=gettingType()
	changeColumnNameType(field,newName,tp,tableName) 
	
def BackToStart():
	start()

def DDL():
	print  "----------------------------"
	print "1 : Create Database"
	print "2 : Show Database"
	print "3 : check Database"
	print "4 : use database"
	print "5 : show tables"
	print "6 : describe table"
	print "7 : create new table"
	print "8 : cretae new table from existing table"
	print "9 : rename table"
	print "10 : drop table"
	print "11 :add new column in table"
	print "12 :remove column from table " 
	print "13 :change column name and type "
	print "14 : back"
	print  "----------------------------"
	ch = input(" Enter your choice : ")
	switcher={
		1:CreateDatabase,
		2:ShowDatabase,
		3:CheckDatabase,
		4:UseDatabase,
		5:ShowTables,
		6:DescribeTable,
		7:CreateNewTable,
		8:CreateNewTableFromExisting,
		9:RenameTable,
		10:DropTable,
		11:AddNewColumnInTable,
		12:RemoveColumnInTable,
		13:ChangeColumnNameAndType,
		14:BackToStart
		}
	ou = switcher.get(ch,"Invalid choice ")
	ou()
	DDL()
def InsertAllField():
	tableName=getChoiceTable()
	lists=forInsert(tableName)
	nameList =[]
	valueList=[]
	for l in lists:
		checkAtInce = l[5].encode('ascii') # if auto_increment then return  auto_increment otherwise empty 
		if(checkAtInce != "auto_increment"):
			name = l[0].encode('ascii')
			value =raw_input("Enter "+name+" : " )
			nameList.append(name)
			valueList.append(value)
	insertRow(tableName,nameList,valueList)

def BackToDML():
	DML()

def Insert():
	print  "----------------------------"
	print "1 : Insert all field "
	print "2 : back "
	print  "----------------------------"
	choice =input("Enter your choice  :  ")
	switcher ={
		1:InsertAllField,
		2:BackToDML
		}
	out = switcher.get(choice ," Invalid choice ")
	out()
	Insert()

def  KeyField():
	tableName=getChoiceTable()
	keyField = getKeyFieldName(tableName)
	getKeyFieldData(tableName,keyField)

def  AllData():
	tableName=getChoiceTable()
	getAllData(tableName)

def  SingleRowByKey():
	tableName=getChoiceTable()
	keyField = getKeyFieldName(tableName)
	value=raw_input(" Enter "+keyField+"  :  " )
	getSingleRowByKeyField(tableName,keyField,value)

def  GetSpecificColumn():
	tableName=getChoiceTable()
	ls = getColumnNameTable(tableName)
	lsName =[]
	print " Enter yes or no for getting field "
	for l in ls:
		n = raw_input(l+" : ")
		if(n == "yes"):
			lsName.append(l)	
	getSpecificColumn(tableName,lsName)

def getLogical():
	print  "----------------------------"
	print "1 : AND "
	print "2 : OR "
	print  "----------------------------"
	n = input(" Enter your choice :  "  )
	switcher ={
		1:"AND",
		2:"OR"
		}
	ou = switcher.get(n, "Invalid choice  ")
	return ou

def getOperator():
	print  "----------------------------"
	print "1 : =="
	print "2 : !="
	print "3 : >="
	print "4 : <="
	print "5 : >"
	print "6 : <"
	print "7 : like"
	print  "----------------------------"
	n =input("Enter your choice  : ")
	switcher ={
		1:"==",
		2:"!=",
		3:">=",
		4:"<=",
		5:">",
		6:"<",
		7:"like"
		}
	ou = switcher.get(n ," Invalid choice ")
	return ou

def addFurtherCondition(ch,sql,ls):
	while(ch =='y'):
		o1 = getLogical()
		o2 = condField(ls)
		o3 = getOperator()
		sql =sql+" "+o1+" "+o2+" "+o3
		val = raw_input(sql+"  : " )
		if(o3 == "like"):
			val = "%"+val+"%" # this is add for like operator	
		sql = sql+" "+val
		ch = raw_input( " Want to add further condition  then press 'y' otherwise anyrhing :  " )
	
	return sql
			

def  GetSpecificColumnByCondition():
	tableName=getChoiceTable()
	ls = getColumnNameTable(tableName)
	listField =[]
	print " Enter yes or no "
	for l1 in ls:
		n = raw_input(l1+" : ")
		if(n == "yes"):
			lsField.append(l1)
	print "1: where"
	print "2: order"
	n1 = input(" Enter your choice  : ")
	clause={
		1:"where",
		2:"order"
		}
	o1=clause.get(n1," Invalid choice ")	
	field = condField(ls)
	sql=""
	if(o1 =="where"):
		o2 = getOperator()
		sql = " where "+field+" "+o2+" "
		value = raw_input(sql+"  ")# no matter we pt the int value b/z it is in string and in database string type is compatable with int,flo
		if(o2 == "like"):
			value = "%"+value+"%" # this is add for like operator		
		sql =sql+value
		print " If u want to add further condition then press y otherwise anything   :  "
		ch = raw_input(" Enter your choice  :  ")
		if(ch =='y'):
			sql = addFurtherCondition(ch,sql,ls)
		
	elif(o1 == "order"):
		sql="order by  "+field
		print  "----------------------------"
		print " 1 : desc "
		print " 2 : asc "
		print  "----------------------------"
		chOrder = input(" Enter your choice :  ")
		orderSwitch ={
			1: "desc",
			2: "asc"
			}
		ouOrder =orderSwitch.get(chOrder, "Invalid choice ")
		sql = sql+"  "+ouOrder			
		print "Have you want to limit the data then press 'yes' otherwise anything  "
		limitChoice = raw_input("Enter your choice  :  ")
		if(limitChoice == 'yes'):
			limitValue =input(" Enter the limit value  :  ")
			sql= sql+" limit  "+limitValue	

	getSpecificRowByCondition(tableName,listField,sql)

def  GetByMinOrMaxField():
	tableName=getChoiceTable()
	sql = "select * from "+tableName+" where "
	lsField=getNumericField(tableName)
	i=1
	for l in lsField:
		print i," . "+l
	n2 = input(" Enter your choice :  ")
	j=1	
	switcher={} # act as switcher
	for l3 in lsField:
		switcher[j]=l3
		j=j+1
	field = switcher.get(n2, "Invalid choice  ")
	print " choose either max or min to get the enterd field  "
	print  "----------------------------"
	print " 1 . max"
	print " 2 . min"
	print  "----------------------------"
	n3 =input(" Enter your choice  : ")
	switcher ={
		1:"max",
		2:"min"		
		}
	ou = switcher.get(n3," invalid choice ")	
	sql = sql+field+" = ( select "+ou+"("+field+") from "+tableName+" ) "
	getAllColumnByMaxMin(sql,tableName)

def  GetByInOrNotinField():
	tableName=getChoiceTable()
	ls = getColumnNameTable(tableName)	
	listField =[]
	print " Enter yes or no "
	for l1 in ls:
		n = raw_input(l1+" : ")
		if(n == "yes"):
			lsField.append(l)
	field = condField(ls)
	print  "----------------------------"
	print " 1 : IN "
	print " 2 : NOT IN "
	print  "----------------------------"
	choice  =input(" Enter your choice  : ")
	switcher={
		1:"IN",
		2:"NOT IN"		
		}
	oper = switcher.get(choice, " invalid choice ")
	getSpecificColumn(tableName,list(field))
	inNotinList=[]
	ch= 'yes'
	print " Enter the value from above list "
	while(ch=='yes'):
		n =raw_input(" Enter : ")
		inNotinList.append(n)
		print " want to add further value then press 'yes' otherwise anything  "
		ch =raw_input(" Enter your choice  : ")
	inNotinTuple= tuple(inNotinList)
	getRowByInNotin(tableName,listField,field,oper,inNotinTuple)

def   GetAggregateValue():
	tableName=getChoiceTable()
	ls = getNumericField(tableName)
	field = condField(ls)
	print  "----------------------------"
	print "1 : average "
	print "2 : minimum "
	print "3 : maximum "
	print "4 : sum "
	print "5 : count"
	print  "----------------------------"
	choice =input(" Enter your choice  :  ")
	switcher= {
		1:"avg",
		2:"min",
		3:"max",
		4:"sum",
		5:"count"
	}
	func = switcher.get(choice, "invalid choice")
	showAggregateValue(tableName,field,func)
	

def Read():
	print  "----------------------------"
	print "1 : Key Field  "
	print "2 : All data "
	print "3 : Single row by key "
	print "4 : Get specific column "
	print "5 : Get specific column by condition "
	print "6 : Get by maximum or minimum value field "
	print "7 : Get by IN or NOT IN field"
	print "8 : Get Aggregate value of field"
	print "9 : Back "
	print  "----------------------------"
	choice =input(" Enter your choice  :  ")
	switcher={
		1:KeyField,
		2:AllData,
		3:SingleRowByKey,
		4:GetSpecificColumn,
		5:GetSpecificColumnByCondition,
		6:GetByMinOrMaxField,
		7:GetByInOrNotinField,
		8:GetAggregateValue,
		9:BackToDML		
		}
	out = switcher.get(choice, "Invalid choice ")
	out()
	Read()

def  UpdateValueInAll():
	tableName=getChoiceTable()
	lsNummericField = getNumericField(tableName)
	i=1
	for l2 in lsNumericField:
		print i," : "+l2
		i=i+1
	n2 = input(" Enter your choice :  ")
	j=1	
	switcher={} # act as switcher
	for l3 in lsNumericField:
		switcher[j]=l3
		j=j+1
	field = switcher.get(n2, "Invalid choice  ")
	value =input(" Enter the value  :  ")
	updateValueInAll(tableName,field,value)

def  UpdateValueInSpecific():
	tableName=getChoiceTable()
	getAllData(tableName)
	keyField = getKeyFieldName(tableName) # we have the name of field which is primary key
	keyValue =raw_input(" Enter "+keyField+" which we want to update  :  ")
	print " ------- Old Value ------"	
	getSinleRow(tableName,keyField,keyValue)
	lsField=getColumnNameTable(tableName) # return all field in table
	updateField=[]	
	print " which field we want to update Enter yes or no "
	for l1 in lsField:
		if(l1 != keyField): # not update the primary key value
			n = raw_input(l1+" : ")
			if(n == "yes"):
				updateField.append(l1)
	updateValue=[]
	for l2 in updateField:
		val = raw_input(l2+" : ")
		updateValue.append(val)
	
	updateValueInSpecific(tableName,updateField,updateValue,keyField,keyValue)

def Update():
	print  "----------------------------"
	print "1 : Update value in all "
	print "2 : Update value in specific"
	print "3 : back "
	print  "----------------------------"
	choice =input(" Enter the choice  :  " )
	switcher={
		1:UpdateValueInAll,
		2:UpdateValueInSpecific,
		3:BackToDML
	}	
	out = switcher.get(choice,"invalid choice ")
	out()
	Update()

def addDeleteOperator(choice,keyField):
	sql =""
	while(choice == "yes"):
		print  "----------------------------"
		print " 1 : = "
		print " 2 : >= "
		print " 3 : <= "
		print " 4 : > "
		print " 5 : < "
		print " 6 : Between "
		print " 7 : IN "
		print " 8 : NOT IN "
		print  "----------------------------"
		ch =input(" Enter your choice  :  ")
		switcher={
			1:"=",
			2:">=",
			3:"<=",
			4:">",
			5:"<",
			6:"Between",
			7:"IN",
			6:"NOT IN"
		}
		oper =switcher.get(ch ," Invalid choice ")
		if(oper == "Between " ):
			print " Enter the range you want to delete "
			strt = raw_input( " Enter the start rof range  :  ")
			end = raw_input(" Enter the end of range  :  ")
			sql = sql+" "+keyField+"  Between "+strt+" AND "+end+" "
	
		elif(oper ==" IN"):
			lsIn =[]
			print " Enter the "+keyField
			ch = "y"
			while(ch=='y'):
				n =raw_input(" Enter : ")
				lsIn.append(n)
				print " want to add further value then press 'y' otherwise anything  "
				ch =raw_input(" Enter your choice  : ")
			tupleIn =tuple(lsIn)
			sql =sql+keyField+"  IN "+tupleIn+"  "
	
		elif(oper =="NOT IN"):
			lsNotin =[]
			print " Enter the "+keyField
			ch = "y"
			while(ch=='y'):
				n =raw_input(" Enter : ")
				lsNotin.append(n)
				print " want to add further value then press 'y' otherwise anything  "
				ch =raw_input(" Enter your choice  : ")
			tupleNotin =tuple(lsNotin)
			sql =sql+keyField+" NOT IN "+tupleNotin+"  "

		else:
			print  " Enter the "+keyField+"  which we want to delete "
			val = raw_input(keyField+"  :  ")
			sql =sql+keyField+oper+val+" "
			
		print "If we want to add further condition then press 'yes' otherwise  anything  "
		choice =raw_input(" Enter choice   :  ")
		if(choice == "yes"):
			sql =sql+" AND  "
	
	return sql

def  DeleteWithConditional():
	tableName=getChoiceTable()
	getAllData(tableName)
	keyField = getKeyFieldName(tableName) # we have the name of field which is primary key
	choice = "yes"	
	sql = addDeleteOperator(choice,keyField)
	delete(tableName,sql)

def Delete():
	print  "----------------------------"
	print "1 : Delete with conditional value "
	print "2 : back"
	print  "----------------------------"
	choice = input(" Enter the choice  :  ")
	switcher={
		1:DeleteWithConditional,
		2:BackToDML
	}
	out= switcher.get(choice," Invalid choice " )
	out()
	Delete()


def DML():
	print  "----------------------------"
	print "1 : Insert "
	print "2 : Read"	
	print "3 : update "
	print "4 : delete "
	print "5 : back "
	print  "----------------------------"
	choice = input(" Enter your choice  :  ")
	switcher={
		1:Insert,
		2:Read,
		3:Update,
		4:Delete,
		5:BackToStart		
	}	
	out = switcher.get(choice ," invalid choice  ")
	out()

def exit():
	sys.exit(0)

def start():
	print  "----------------------------"	
	print "1 : DDL"
	print "2 : DML"
	print "3 : exit"
	print  "----------------------------"
	ch = input(" Enter your choice : ")
	switcher={
		1:DDL,
		2:DML,
		3:exit	
		}
	ou = switcher.get(ch,"Invalid choice ")
	ou()

start()
