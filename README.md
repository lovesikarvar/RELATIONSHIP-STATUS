# RELATIONSHIP-STATUS
Develop a flames game using python. Flames is a popular game named after the acronym: Friends, Lovers, Affectionate, Marriage, Enemies, Sibling. This game does not accurately predict whether or not an individual is right for you, but it can be fun to play this with your friends.
def flames(name1, name2):
  """Calculates the FLAMES relationship result between two names.

  Args:
    name1: The first name.
    name2: The second name.

  Returns:
    A string representing the FLAMES relationship result:
      "Friends", "Lovers", "Affectionate", "Marriage", "Enemies", "Siblings".
  """

  # Remove common characters from the names, case-insensitive
  name1 = name1.lower()
  name2 = name2.lower()
  for char in name1:
    if char in name2:
      name1 = name1.replace(char, '', 1)
      name2 = name2.replace(char, '', 1)

  # Calculate the total number of remaining letters
  total_letters = len(name1) + len(name2)

  # FLAMES acronym
  flames = ["Friends", "Lovers", "Affectionate", "Marriage", "Enemies", "Siblings"]

  # Remove letters from FLAMES based on the count
  while len(flames) > 1:
    index = (total_letters % len(flames)) - 1
    if index < 0:
      index = len(flames) - 1
    del flames[index]

  # Return the remaining FLAMES relationship
  return flames[0]


# Get input names
name1 = input("Enter the first name: ")
name2 = input("Enter the second name: ")

# Calculate and print the FLAMES result
result = flames(name1, name2)
print("Relationship status:", result)
