//
//  LeftSideViewController.swift
//  PinPad
//
//  Created by Jacob Sharp on 10/29/15.
//  Copyright © 2015 Alian Development. All rights reserved.
//

import UIKit
import Parse
import Bolts

@available(iOS 9.0, *)
class LeftSideViewController: UIViewController, UITableViewDelegate {
    
    @IBOutlet var Profilepic: UIImageView!
    
    @IBOutlet var Name: UILabel!
    
    @IBOutlet var Username: UILabel!
    
    @IBAction func Profile(_ sender: AnyObject) {
        
        let openprofile = self.storyboard?.instantiateViewController(withIdentifier: "ProfileViewController") as! ProfileViewController
        
        let openprofileNav = UINavigationController(rootViewController: openprofile)
        
        let appDelegate = UIApplication.shared.delegate as! AppDelegate
        
        appDelegate.centerContainer!.centerViewController = openprofileNav
        appDelegate.centerContainer!.toggle(MMDrawerSide.left, animated: true, completion: nil)
        
    }
    
    @IBAction func News(_ sender: AnyObject) {
        
        let openbusiness = self.storyboard?.instantiateViewController(withIdentifier: "BusinessViewController") as! BusinessViewController
        
        let openbusinessNav = UINavigationController(rootViewController: openbusiness)
        
        let appDelegate = UIApplication.shared.delegate as! AppDelegate
        
        appDelegate.centerContainer!.centerViewController = openbusinessNav
        appDelegate.centerContainer!.toggle(MMDrawerSide.left, animated: true, completion: nil)
    }
    
    @IBAction func Waves(_ sender: AnyObject) {
        
        let openwaves = self.storyboard?.instantiateViewController(withIdentifier: "WavesViewController") as! WavesViewController
        
        let openwavesNav = UINavigationController(rootViewController: openwaves)
        
        let appDelegate = UIApplication.shared.delegate as! AppDelegate
        
        appDelegate.centerContainer!.centerViewController = openwavesNav
        appDelegate.centerContainer!.toggle(MMDrawerSide.left, animated: true, completion: nil)
    }
    
    @IBAction func Findfriends(_ sender: AnyObject) {
        
        let openfindfriends = self.storyboard?.instantiateViewController(withIdentifier: "FindFriendsViewController") as! FindFriendsViewController
        
        let openfindfriendsNav = UINavigationController(rootViewController: openfindfriends)
        
        let appDelegate = UIApplication.shared.delegate as! AppDelegate
        
        appDelegate.centerContainer!.centerViewController = openfindfriendsNav
        appDelegate.centerContainer!.toggle(MMDrawerSide.left, animated: true, completion: nil)
        
    }
    
    @IBAction func Settings(_ sender: AnyObject) {
        
        let opensettings = self.storyboard?.instantiateViewController(withIdentifier: "SettingsViewController") as! SettingsViewController
        
        let opensettingsNav = UINavigationController(rootViewController: opensettings)
        
        let appDelegate = UIApplication.shared.delegate as! AppDelegate
        
        appDelegate.centerContainer!.centerViewController = opensettingsNav
        appDelegate.centerContainer!.toggle(MMDrawerSide.left, animated: true, completion: nil)
        
    }
    
    @IBAction func Logout(_ sender: AnyObject) {
        
        PFUser.logOut()
        
        let logout = self.storyboard?.instantiateViewController(withIdentifier: "ViewController") as! ViewController
        
        let logoutNav = UINavigationController(rootViewController: logout)
        
        let appDelegate = UIApplication.shared.delegate as! AppDelegate
        
        appDelegate.centerContainer!.centerViewController = logoutNav
        appDelegate.centerContainer!.toggle(MMDrawerSide.left, animated: true, completion: nil)
        
    }
    
    override func viewDidLoad() {
        super.viewDidLoad()
        
        Profilepic.layer.cornerRadius = 10
        Profilepic.clipsToBounds = true
        
        self.navigationController?.isNavigationBarHidden = true
        
    }
    
    override func viewWillAppear(_ animated: Bool) {
        
        loadUserDetails()
    }
    
    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
        // Dispose of any resources that can be recreated.
    }
    
    
    //////////////////////////////////
    //Load User Information from Parse
    
    func loadUserDetails()
    {
        
        let userFirstName = PFUser.current()?.object(forKey: "first_name") as! String
        let userLastName = PFUser.current()?.object(forKey: "last_name") as! String
        let username = PFUser.current()?.object(forKey: "username") as! String

        Username.text = ">\(username)"
        Name.text = "\(userFirstName) \(userLastName)"
        
        let profilepictureobject = PFUser.current()?.object(forKey: "profile_photo") as! PFFile
    
        profilepictureobject.getDataInBackground { (imageData:Data?, error:Error?) -> Void in
    
            if (imageData != nil)
            {
    
                self.Profilepic.image = UIImage(data: imageData!)
            }
    
        }
    }


        //END Load User info from Parse
        ///////////////////////////////
    
    
}
