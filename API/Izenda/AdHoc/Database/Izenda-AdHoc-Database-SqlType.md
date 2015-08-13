#SqlType

[[_TOC_]]

##Enum Properties 

* Null -  Type not set. 
* Unknown -  An unknown type. 
* Boolean -  Boolean (bit). 
* SByte -  Signed Byte (8 bit integer). 
* Byte -  Unsigned byte. 
* Int16 -  Small integer (16 bit integer). 
* UInt16 -  Unsigned small integer (word). 
* Int32 -  Integer (32 bit integer). 
* UInt32 -  Unsigned integer. 
* Int64 -  Long integer (64 bit integer). 
* UInt64 -  Unsigned long integer. 
* Float -  Floating point number data from –3.40E + 38 through 3.40E + 38.  Storage size is 4 bytes. 
* Double -  Floating point number data from - 1.79E + 308 through 1.79E + 308. Storage size is 8 bytes. 
* Decimal -  Numeric data type with fixed precision and scale. 
* SmallMoney -  Monetary data values from - 214,748.3648 through +214,748.3647,  with accuracy to a ten-thousandth of a monetary unit.  Storage size is 4 bytes.  
* Money -  Monetary data values from -2^63 (-922,337,203,685,477.5808) through 2^63 - 1 (+922,337,203,685,477.5807), with accuracy to a ten-thousandth of a monetary unit.  Storage size is 8 bytes. 
* SmallDateTime -  Date and time data from January 1, 1900, through June 6, 2079,  with accuracy to the minute. smalldatetime values with 29.998 seconds  or lower are rounded down to the nearest minute; values with 29.999  seconds or higher are rounded up to the nearest minute. Storage size is 4 bytes.  
* DateTime -  Date and time data from January 1, 1753 through December 31, 9999,  to an accuracy of one three-hundredth of a second (equivalent to 3.33  milliseconds or 0.00333 seconds). Values are rounded to increments  of .000, .003, or .007 seconds. Storage size is 8 bytes.  
* AnsiChar -  Fixed-length non-Unicode character data with length of n bytes.  n must be a value from 1 through 8,000. Storage size is n bytes.  The SQL-92 synonym for char is character. 
* AnsiVarChar -  Variable-length non-Unicode character data with length of n bytes.  n must be a value from 1 through 8,000. Storage size is the actual  length in bytes of the data entered, not n bytes. The data entered  can be 0 characters in length. The SQL-92 synonyms for varchar are  char varying or character varying. 
* AnsiText -  Variable-length non-Unicode data in the code page of the server and  with a maximum length of 231-1 (2,147,483,647) characters. 
* AnsiVarCharMax -  Variable-length non-Unicode data in the code page of the server and  with a maximum length of 231-1 (2,147,483,647) characters. 
* Char -  Fixed-length Unicode character data of n characters.  n must be a value from 1 through 4,000. Storage size is two times n bytes.  The SQL-92 synonyms for nchar are national char and national character. 
* VarChar -  Variable-length Unicode character data of n characters.  n must be a value from 1 through 4,000. Storage size, in bytes, is two times  the number of characters entered. The data entered can be 0 characters in length.  The SQL-92 synonyms for nvarchar are national char varying and national character varying. 
* Text -  Variable-length Unicode data with a maximum length of 230 - 1 (1,073,741,823)  characters. Storage size, in bytes, is two times the number of characters entered.  The SQL-92 synonym for ntext is national text. 
* VarCharMax -  Variable-length Unicode data with a maximum length of 230 - 1 (1,073,741,823)  characters. Storage size, in bytes, is two times the number of characters entered.  
* Binary -  Fixed-length binary data of n bytes. n must be a value from 1 through 8,000.  Storage size is n+4 bytes.  
* VarBinary -  Variable-length binary data of n bytes. n must be a value from 1 through 8,000.  Storage size is the actual length of the data entered + 4 bytes, not n bytes.  The data entered can be 0 bytes in length.  The SQL-92 synonym for varbinary is binary varying. 
* Image -  Variable-length binary data from 0 through 231-1 (2,147,483,647) bytes.  
* VarBinaryMax -  Variable-length binary data from 0 through 231-1 (2,147,483,647) bytes.  
* Variant -  A data type that stores values of various SQL Server-supported data types,  except text, ntext, image, timestamp, and sql_variant.  
* TimeStamp -  A datatype typically used to store automatically generated binary numbers, which are guaranteed to be unique within a database.  Timestamps are typically used as a mechanism for version-stamping table rows. The storage size is 8 bytes. 
* GUID -  A globally unique identifier (GUID).  
* Date -  Defines a date in SQL with a storage size of 3 to 5 bytes.  
* Time -  Defines a time of a day in SQL without timezone awareness, based on a 24-hour clock. 