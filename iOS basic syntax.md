# iOS basic syntax

## Declare 
### constant

	Let pi = 3.141592653589793 

### variable
	var des: String?
	print(des!)
	Print("pi is \(pi)")

## switch case
	Switch ingrediant{
	Case "tomato":
		Print()
	Case "bean":
		Print()
	}

## set image view
	imageView.image = UIImage(named :"")

## string
	randomStr.insert("A", at: randomStr.startIndex)
	randomStr.insert("A", at: randomStr.index(randomStr.startIndex, offset: 2))

## arrays

## Dictionary

	Var dict1 = [Int : String]()
	Var dict2 : [Int : String] = [1:"",2:""]

## Enum	
	Enum carType{
		case a
		case b
	}


## class

	Var typeofcar :CarType = .a
	
	
	Class ViewController: UIViewController{
		override function viewDIdLoad{
			super.viewdidLoad()
			mystuff()
		}
	}

## Layout
Automatically make label fit the words inside it: command+ =

self.view.frame.width
Self.view.frame.height

Nest image views inside a View, creating child parent relationship

### Pining
a fixed distance from the screen, square will expand from small screen to large screen
### Alignment
keep the square the same size, fixed width and height, always in the centre





Info.plist
	Privacy-location when in use 
	locationwheninuseAthurization
