# COP2664-1-Lesson-7-Programming-Exercise-Rental-Car-System
This repository link is a submission link for COP2664-1: Lesson 7 Programming Exercise Rental Car System

// This program is designed for a car rental system where it puts down the availibility of cars, models, and status if they are available or not.

enum VehicleStatus {
    case available
    case rented
    case maintenance
} // This is the enum for the status of the vehicles.
struct VehicleDetails {
    let make: String
    let model: String
    let year: Int
} // This is the struct for the vehicle details.
class Vehicle {
    var id: Int
    var type: String
    var status: VehicleStatus
    var details: VehicleDetails // This is the class for the vehicles.
    init(id: Int, type: String, status: VehicleStatus, details: VehicleDetails) { 
        self.id = id
        self.type = type
        self.status = status
        self.details = details
    } // This is the init for the vehicle class.
    func rent() {
        if status == .available {
            status = .rented
        }
    } // This is the function for renting the vehicles.
    func returnToFleet() {
        if status == .rented {
            status = .available
        }
    } // This is the function for returning the vehicles.
    func sendToMaintenance() {
        if status == .rented {
            status = .maintenance
        }
    } // This is the function for sending the vehicles to maintenance.
    func displayDetails() {
        print("Vehicle ID: \(id)")
        print("Type: \(type)")
        print("Status: \(status)")
        print("Make: \(details.make)")
        print("Model: \(details.model)")
        print("Year: \(details.year)")
    } 
} // This is the function for displaying the vehicles.
let vehicle1 = Vehicle(id: 115, type: "Car", status: .available, details: VehicleDetails(make: "Lexus", model: "LFA", year: 2012))
let vehicle2 = Vehicle(id: 102, type: "Motorbike", status: .rented, details: VehicleDetails(make: "Suzuki", model: "Hayabusa", year: 2021))
let vehicle3 = Vehicle(id: 129, type: "Pickup Truck", status: .maintenance, details: VehicleDetails(make: "Ford", model: "F-150", year: 1993)) // This is the vehicles.
vehicle1.displayDetails()
vehicle2.displayDetails()
vehicle3.displayDetails() // This is the display for the vehicles.
vehicle1.rent()
vehicle2.returnToFleet()
vehicle3.sendToMaintenance() // This is the functions for the vehicles.
