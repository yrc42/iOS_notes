# iOS basic syntax

## Declare 
### constant

	Let pi = 3.141592653589793 

### variable
	var des: String?
	print(des!)
	Print("pi is \(pi)")
	
### Optional Binding
if let constName = optionalName {

}
### Conversion
	let str = String(aNumber)

## switch case: no fall through
	Switch ingrediant{
	Case "tomato":
		Print()
	Case "bean":
		Print()
	default:
		print()
	}


## string
### startIndex & endIndex & offsetBy
	randomStr.insert("A", at: randomStr.startIndex)
	randomStr.insert("A", at: randomStr.index(randomStr.startIndex, offsetBy: 2))
### index: of
	let greeting = "Hello, World"
	var index = greeting.index(of : ",") ?? greeting.endIndex
	let begining = greeting[..<index]
	let helloString = String(begining)
### hasPrefix & hasSuffix
	if string.hasPrefix("hel")


## arrays
	let emptyArray = [String]()
	var list :[String] = ["A", "B"]
	var threeInts = Array(repeating : 0, count:3)
`count`,`isEmpty`, `append`, `insert("a", at:3)`
	
	for item in list{}
	for (item, value) in list.enumerated(){}
	
## Set

	var favouriteGenres: Set<String> = ["rock", "pop"]
	`count`,`isEmpty`, `append`,`contain`, `sorted`
	oddDigits.union(evenDigit)
	`isSubset`,`isDisjoint`

## Dictionary

	Var dict1 = [Int : String]()
	Var dict2 : [Int : String] = [1:"",2:""]
	for (key, item) in dict1 {
	
	}
	if let airportName = airports["YYZ"] {
		print(airportName)
	}else{
		print("such airport not in the dict"
	}

## Enum	
	enum carType{
		case a
		case b
	}
	Var typeofcar :CarType = .a
	
	enum ServerResponse {
		case result(String),
		case failure(String)
	}
## Functions
	func greeting(person: String)-> String {
	
	}
	greeting(person:"Dave")  
** add `mutating` in front of `func` if function will change the class that it is inside of.**
		
### inout parameter: values changed inside the function
	func swap (a : inout Int, b: inout Int)
	swap(a:&someInt, b: &otherInt)
### return tuple
	fuc calc (scores : [Int]) -> (min:Int, max: Int) {
		return (min, max)
	}	
### return fucntion
	func increment() -> ( (int) -> int ) {
		func addOne (num:Int) - > Int {
			return num+1
		}
		return addOne
	}
	var incre = increment()
	incre(10)
	
### takes in function
	func hasMatches(list: [Int], condition:(Int) ->Bool)) -> Bool {
		
	}
	func greaterThanFour(){
	
	}
	hasMatches(list: [1,2,3,4], condition: greaterThanFour)
	
#### map
	let mappedNumber = nums.map({num in 3*num})
#### sort
	let sortedNumber = nums.sorted { $0 < $1 }
### loops
	for i in 0..<4 {
		//i will be 0,1,2,3
	}
	for i in 0...4 {
		//i will be 0,1,2,3,4
	}
	
## Generic Functions

## class

	
class and parent class name:
	
	Class ViewController: UIViewController{
		override function viewDIdLoad{
			super.viewdidLoad()
			mystuff()
		}
	}

## Error Handling

	do {
		try canThrowError()
		
	} catch {
	
	}


## Info.plist
	Privacy-location when in use 
	locationwheninuseAthurization

## Cocoapods vs Carthage
a dependency manager

1. install at terminal
	`sudo gem install cocoapods`
2. `pod setup --verbose`
3. `pod init`
4. go into podfile and edit it: `pod 'SwiftJSON'`
5. 






