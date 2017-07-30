# Sound
`import AVFoundation`

	class ViewController: UIViewController, AVAudioPlayerDelegate{
    	
    	var audioPlayer = AVAudioPlayer()

   		 @IBAction func notePressed(_ sender: UIButton) {
	       //sender's tag is set in attribute view
	        var selectedSoundFile : String = array[sender.tag-1]
	        //where the sound us located
	        let url = Bundle.main.url(forResource: selectedSoundFileName, withExtension: "wav")!
	        do{
	            audioPlayer = try AVAudioPlayer(contentsOf:url)
	        }
	        catch{
	            print(error)
	        }
	        audioPlayer.play()
	     }
	}


# Alert

## Action Sheet
bottom of the screen
## modal alert
a popup in the middle of the screen with number of actions to choose from
`import UIAlertController`

	let alert = UIAlertController(title: "finished", message:"would you like to start over?", preferredStyle:.alert)
	let restartAction = UIAlertAction(title:"restart", style: .default, handler:{
		(UIAlertAction) in self.startOver()
	})
	alert.addAction(restartAction)
	present(alert, animated: true, completion:nil)



# Location
`import CoreLocation`

WeatherViewController handles information sent from CoreLocation, something written by Apple.

	class WeatherViewController: UIViewController, CLLocationManagerDelegate, ChangeCityDelegate {
    
       //TODO: Declare instance variables here
    	let locationManager = CLLocationManager()
    	
    	override func viewDidLoad() {
       	 super.viewDidLoad()
        
        //TODO:Set up the location manager here. set ourself as the delegate
        	locationManager.delegate = self
        	locationManager.desiredAccuracy = kCLLocationAccuracyHundredMeters
        	locationManager.requestWhenInUseAuthorization()
       
        	locationManager.startUpdatingLocation() //async, send msg to viewcontroller when location updated
        	}
        
    }


# Photo library

* add bar button item and change system item= camera in attribute inspector
* image view: to display to image chosen
* class ViewController: UIViewController, **UIImagePickerControllerDelegate**, **UINavigationControllerDelegate**{}
* imagePicker.delegate = self
	
		@IBAction func cameraTapped(_ sender: UIBarButtonItem) { 
	        imagePicker.sourceType = .savedPhotosAlbum
	        imagePicker.allowsEditing = false
	        present(imagePicker, animated: true, completion: nil)
	        
	    }
		 func imagePickerController(_ picker: UIImagePickerController, didFinishPickingMediaWithInfo info: [String : Any]) {
			  cameraButton.isEnabled = false
			  SVProgressHUD.show()
			  if let image = info[UIImagePickerControllerOriginalImage] as? UIImage{
            
            imageView.image = image
            dismiss(animated: true, completion: nil)    
		}
		
		