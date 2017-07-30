# Delegation

Between View Controllers: pass information from one view controller to the next, create a instance of that second controller.   
Say if we need to send information from class A to class B: we can create B1 an instance of B, B1 is now stacked upon the other ViewController, and the ViewControllers can be dissmissed.
 
	B1.data = 123

However, CoreLoation(created by apple) find the location and send the location message to the view controller.
CoreLocation does not know what properties are inside our ViewController, thus delegation is required, as **it sends the info to the delegate**.


# Segue

### Sending ViewController: 
	
* A textfield, user input
* A button
* in Viewcontroller.swift, create IBAction for the button 
		
		@IBAction func buttonPressed(_ sender: Any)
		{
			 performSegue(identifier: "goToSecondScreen", sender: self)
		}
		
		Override Prepare(forSegue, sender){
			// Check if the seque identifier is the seque we want
			// Pass the value of text field to second controller
			
			Let destinationVC = seg.destination as! SecondViewController
			destinationVC.textPassedOver = textField.text
		}

### Receiving ViewController
* A Label to display text
* a string: var textPassedOver: String?
 		
 		label.text = textPassedOver

## Steps

* Button at VC1 --->(press control key and drag it over )--->present ViewController2
* Create a class for the second VC, change the class name of second VC to the same as the file name
* Name the segue identifier in attribute inspector
* create buttonPressed and prepare function in VC1
* set label value in VC2


## Example

WeatherViewController as the delegate of ChangeCityVC, to manage information from ChangeCity
In other words ChangeCity sends info and WeatherView handles it. 

1. Create protocol in ChangeCity,now Weather must inplement this function
		
		protocol ChangeCityDelegate{
		    func userEnteredANewCityName(city: String)
		}
		
		class ChangeCityViewController: UIViewController {
    
    		//Declare the delegate variable here:
    		var delegate : ChangeCityDelegate? //a ViewController can declare itself
    
    		//This is the pre-linked IBOutlets to the text field:
    		@IBOutlet weak var changeCityTextField: UITextField!
    
    		//This is the IBAction that gets called when the user taps on the "Get Weather" button:
    		@IBAction func getWeatherPressed(_ sender: AnyObject){
    			//1 Get the city name the user entered in the text field
        		let cityName = changeCityTextField.text

        		//2 If we have a delegate set, call the method userEnteredANewCityName
        		delegate?.userEnteredANewCityName(city: cityName!)
        
        		//3 dismiss the Change City View Controller to go back to the WeatherViewController
        		self.dismiss(animated: true, completion: nil)
        	}
        	
        	//This is the IBAction that gets called when the user taps the back button. It dismisses the ChangeCityViewController.
    		@IBAction func backButtonPressed(_ sender: AnyObject) {
       			self.dismiss(animated: true, completion: nil) //make this VC go away
    		}
    	}
    	

		
2. Conform to protocol in WeatherVC 
3. Inplement 			
	    //to fulfill the protocol requirement for changecity delegate
	    func userEnteredANewCityName(city: String) {
	        let params : [String : String] = ["q" : city, "appid" : APP_ID]
	        getWeatherData(url: WEATHER_URL, parameters: params)
	        
	    }
	    
	    //Write the PrepareForSegue Method here
	    override func prepare(for segue: UIStoryboardSegue, sender: Any?) {
	        if segue.identifier == "changeCityName" {
	            let destinationVC = segue.destination as! ChangeCityViewController
	            destinationVC.delegate = self
	            
	        }
	    }


	
## Sending information back and forth
If we just use segue for both view controller, we are creating many new view controller objects A->B1->A1->B2. Thus, to truly send data back(second VC to first) we need to use protocals.

1. create protocol in second view controller

		protocal CanReceive{
			func dataReceived(data: String)
		}
	
2. conform to the protocal  and implement it in first view controller (receiving the data)
	
		class firstVC: UIViewController, CanReceive{
			func dataReceived(data: String){
				label.text = data
			}
		}

3. 	create a new property inside the second view controller
		
		var delegate: CanReceive? //can be empty, data may not be sent to anywhere 
		
		@IBAction buttonPressed(){
			delegate?.dataReceived(data: textField.text) 
		}
		
4. set ourselves as the delegate of second VC in first view controller
		
		func prepare(){
			destinationVC.delegate = self
		}
5. dissmiss the second view controller so the first VC displays
		
		@IBAction buttonPressed(){
			delegate?.dataReceived(data: textField.text) 
			dismiss(animated:true, completion:nil)
		}

	
Completion handler
navigation controller: back button, swipe right
Editor, embed in
Custom cell
Register nib file


