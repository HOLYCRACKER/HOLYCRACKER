from datetime import datetime, timedelta

class Reminder:
  """
  A class representing a reminder with title, description, and reminder time.
  """
  def __init__(self, title, description, reminder_time):
    self.title = title
    self.description = description
    self.reminder_time = reminder_time

  def is_due(self):
    """
    Checks if the reminder time has passed the current time.
    """
    return self.reminder_time <= datetime.now()

def create_reminder(title, description, reminder_time):
  """
  Creates a new Reminder object and returns it.
  """
  # Error handling for invalid reminder time can be added here
  return Reminder(title, description, reminder_time)

def list_reminders(reminders):
  """
  Prints the details of all reminders in a list.
  """
  if not reminders:
    print("You don't have any reminders yet!")
  else:
    for reminder in reminders:
      print(f"Title: {reminder.title}")
      print(f"Description: {reminder.description}")
      print(f"Reminder Time: {reminder.reminder_time}\n")

# Sample usage
reminders = []

while True:
  # Display menu options
  print("Schedular Menu:")
  print("1. Add Reminder")
  print("2. List Reminders")
  print("3. Exit")
  
  choice = input("Enter your choice: ")

  if choice == '1':
    title = input("Enter reminder title: ")
    description = input("Enter reminder description (optional): ")
    # Get user input for reminder time (can be improved for better format)
    reminder_time_str = input("Enter reminder time (YYYY-MM-DD HH:MM): ")
    reminder_time = datetime.strptime(reminder_time_str, "%Y-%m-%d %H:%M")
    reminders.append(create_reminder(title, description, reminder_time))
    print("Reminder created successfully!")

  elif choice == '2':
    list_reminders(reminders)

  elif choice == '3':
    print("Exiting Schedular...")
    break

  else:
    print("Invalid choice. Please try again.")

# Check for upcoming reminders after exiting the loop
upcoming_reminders = [reminder for reminder in reminders if not reminder.is_due()]
if upcoming_reminders:
  print("Upcoming Reminders:")
  list_reminders(upcoming_reminders)
else:
  print("You don't have any upcoming reminders.")


- 🌱 feel free to help with this project 
- 💞️ I’m looking to collaborate on this project
- 📫 How to reach me ...46bsns.bsns@gmail.com
  
<!---
HOLYCRACKER/HOLYCRacker
--->
