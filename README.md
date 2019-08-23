# GoLibrarySO

This is a dynamic library compiled by the go language that supports Java calls.  

First：  
```
import "C"  
```

Secondly：  
```go
//export RunGoLibrarySo  
func RunGoLibrarySo(_str *C.char) *C.char {  
	//TODO 接收参数  
	str := C.GoString(_str)  

	//TODO 方法调用并返回值  
	results := C.CString(goMethod(str))  

	return results  
}  

func goMethod(_value string) string {  
	//TODO 业务逻辑处理  

	return _value  
}  
```
Finally throw the program into Linux to compile:
go build -buildmode=c-shared -o main.so ./main.go

So we're going to generate two files here one with the.h end and the other with the so end;When using these two files can be introduced;