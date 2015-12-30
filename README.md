# CodePathAssignments
//
//  ViewController.swift
//  SettingsViewCalculator
//
//  Created by Aaron McLeod on 12/14/15.
//  Copyright © 2015 McLeod Inc. All rights reserved.
//

import UIKit

class ViewController: UIViewController
{

    @IBOutlet weak var BillField:
        UITextField!
    
    @IBOutlet weak var tipLabel:
        UILabel!
    
    @IBOutlet weak var totalLabel:
        UILabel!
    
    @IBOutlet weak var tipControl:
        UISegmentedControl!
    
    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view, typically from a nib.
        
        tipLabel.text = "$0.00"
        totalLabel.text = "$0.00"
        
    }

    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
        // Dispose of any resources that can be recreated.
    }
    @IBAction func OnEditingChanged(sender: AnyObject)
    {
        let num = [0.1, 0.15, 0.2]
        let tipPercetage = num[tipControl.selectedSegmentIndex]

        let billAmount = NSString(string: BillField.text!).doubleValue
        let tip = billAmount * tipPercetage
        let total = billAmount + tip
    
        
        tipLabel.text = String(format: "$%.2f", tip)
        totalLabel.text = String(format: "$%.2f", total)
    }

    @IBAction func onTap(sender: AnyObject)
    {
        view.endEditing(true)
    }

}

