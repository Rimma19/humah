# human
import requests

def count_young_people():
    # Example API endpoint for retrieving demographic data
    api_endpoint = "https://exampleapi.com/demographics"

    try:
        # Assuming the API returns JSON data with demographic information
        response = requests.get(api_endpoint)
        data = response.json()

        # Extract relevant information for young people count
        if 'young_people' in data:
            young_people_count = data['young_people']
            return young_people_count
        else:
            print("Error: Unable to retrieve young people count from API.")
            return None

    except requests.exceptions.RequestException as e:
        print(f"Error fetching data: {e}")
        return None

# Example usage
young_people_count = count_young_people()
if young_people_count is not None:
    print(f"Estimated number of young people in the world: {young_people_count}")
