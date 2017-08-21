#Alamofire + swiftyJson

	func getWeatherData(url: String,parameters: [String:String]){
	 	
	 	Alamofire.request(url, method: .get, parameters: parameters).responseJSON {
            response in //closure: function within a function, waiting for response
            
            if response.result.isSuccess{
                let weatherJSON : JSON  = JSON(response.result.value!) //turn optional to sure, it will not be nill
                self.updateWeatherData(json: weatherJSON)
            }
            else
            {
                print("Error \(response.result.error!)")
            }
            
        }

