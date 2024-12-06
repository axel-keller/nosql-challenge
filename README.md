# nosql-challenge
Module 12 Challenmge
In the NoSQL_analysis_starter I was having trouble getting finding the establishments with London as the Local Authority and has a RatingValue greater than or equal to 4. I had the AI assistant learning check my code and it corrected it to the following..

# Find the establishments with London as the Local Authority and has a RatingValue greater than or equal to 4.
query = {
    "LocalAuthorityName": {"$regex": "London", "$options": "i"},  # 'i' for case-insensitive matching
    "RatingValue": {"$gte": 4}
}

# Use count_documents to display the number of documents in the result
count = db.establishments.count_documents(query)
print(f"Number of documents matching the query: {count}")

# Display the first document in the results using pprint
first_document = db.establishments.find_one(query)
from pprint import pprint
pprint(first_document)

