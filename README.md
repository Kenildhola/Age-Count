# Age-Count

  let birthdate = users1?.value(forKey: "birth_date") as? String
                    if birthdate != nil
                    {
                        let age = self.calcAge(birthday: birthdate ?? "")
                        
                        self.lblName.text = "\(first_name ?? "") \(last_name ?? ""), \(age)"
                        
                        if self.lblName.text == "" || self.lblName.text == " "
                        {
                            self.lblName.text = "\(username ?? ""), \(age)"
                        }

                    }
                    else
                    {
                        self.lblName.text = "\(first_name ?? "") \(last_name ?? "")"
                        
                        if self.lblName.text == "" || self.lblName.text == " "
                        {
                            self.lblName.text = "\(username ?? "")"
                        }


************************** func **********************************

func calcAge(birthday: String) -> Int {
            let dateFormater = DateFormatter()
            dateFormater.dateFormat = "yyyy-MM-dd"
            let birthdayDate = dateFormater.date(from: birthday)
            let calendar: NSCalendar! = NSCalendar(calendarIdentifier: .gregorian)
            let now = Date()
        let calcAge = calendar.components(.year, from: birthdayDate!, to: now, options: [])
            let Age = calcAge.year
            return Age!
        }
