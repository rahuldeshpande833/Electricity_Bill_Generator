# Electricity_Bill_Generator
I created this new Python project for electricity_bill_generator for consumers to check the unit-per-hour electricity bill amount.

class ElectricityBill:
    def __init__(self, customer_name, units_consumed):
        self.customer_name = customer_name
        self.units_consumed = units_consumed

    def calculate_bill(self):
        if self.units_consumed <= 100:
            return self.units_consumed * 3.50
        elif 100 < self.units_consumed <= 300:
            return 100 * 3.50 + (self.units_consumed - 100) * 4.50
        else:
            return 100 * 3.50 + 200 * 4.50 + (self.units_consumed - 300) * 6.00

    def generate_bill(self):
        bill_amount = self.calculate_bill()
        bill_info = f"Customer Name: {self.customer_name}\nUnits Consumed: {self.units_consumed}\nTotal Amount: ${bill_amount:.2f}"
        return bill_info

def main():
    print("Electricity Bill Generator\n")
    customer_name = input("Enter customer name: ")
    units_consumed = float(input("Enter units consumed: "))

    bill = ElectricityBill(customer_name, units_consumed)
    bill_info = bill.generate_bill()

    print("\nBill Details:\n")
    print(bill_info)

if __name__ == "__main__":
    main()

