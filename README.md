import phonenumbers
from phonenumbers import geocoder

def find_location(phone_number):
    try:
        parsed_number = phonenumbers.parse(phone_number, "GB")  # Change "GB" to the appropriate country code
        location = geocoder.description_for_number(parsed_number, "en")
        return location
    except phonenumbers.phonenumberutil.NumberParseException:
        return "Invalid phone number"

phone_number = "+1234567890"  # Replace with the phone number you want to locate
location = find_location(phone_number)
print("Location:", location)
