# iOS basic syntax

## Declare 
### constant

	Let pi = 3.141592653589793 

### variable
	var des: String?
	print(des!)
	Print("pi is \(pi)")
### Conversion
	let str = String(aNumber)

## switch case
	Switch ingrediant{
	Case "tomato":
		Print()
	Case "bean":
		Print()
	default:
		print()
	}

## set image view
	imageView.image = UIImage(named :"")

## string
	randomStr.insert("A", at: randomStr.startIndex)
	randomStr.insert("A", at: randomStr.index(randomStr.startIndex, offset: 2))

## arrays
	let emptyArray = [String]()

## Dictionary

	Var dict1 = [Int : String]()
	Var dict2 : [Int : String] = [1:"",2:""]
	for (key, item) in dict1 {
	
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
## class

	
class and parent class name:
	
	Class ViewController: UIViewController{
		override function viewDIdLoad{
			super.viewdidLoad()
			mystuff()
		}
	}

## Layout
Automatically make label fit the words inside it: `command+ =`
	
	self.view.frame.width
	Self.view.frame.height

Nest image views inside a View, creating child parent relationship

### Pining
a fixed distance from the screen, square will expand from small screen to large screen
### Alignment
keep the square the same size, fixed width and height, always in the centre


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






