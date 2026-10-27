# python-activity-based-learing 
Algorithm
1.Start.
2.Enter vehicle type, entry time, and exit time.
3.Validate time inputs.
4.Calculate parking hours, including overnight parking.
5.Calculate fee based on vehicle type.
6.Add penalty if parking exceeds 24 hours.
7.Apply daily maximum limit and display the bill.
8.Stop.
flowchart
Start
Input vehicle and times
Validate time and calculate hours
Calculate fee and penalty
Apply daily limit and display bill
Stop
vehicle = input("Vehicle (car/bike): ").lower()
entry = int(input("Entry hour (0-23): "))
exit = int(input("Exit hour (0-23): "))

if vehicle not in ["car", "bike"] or entry < 0 or entry > 23 or exit < 0 or exit > 23:
    print("Invalid input")
else:
    hours = exit - entry
    if hours <= 0:
        hours += 24

    if vehicle == "car":
        rate = 20
    else:
        rate = 10

    bill = min(hours * rate, 200)

    if hours > 24:
        bill += 100

    print("Parking hours:", hours)
    print("Total fee: Rs.", bill)
   Vehicle (car/bike): car
Entry hour (0-23): 20
Exit hour (0-23): 6
Parking hours: 10
Total fee: Rs. 200 
