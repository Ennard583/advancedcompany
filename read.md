app_id = 'xxxxxx' #Application Id - on the azure app overview page
client_secret = 'xxxxx' 
#Use the redirect URL to create a token url
token_url = 'https://login.microsoftonline.com/<DIRECTORY (tenant) ID>/oauth2/token'
token_data = {
 ‘grant_type’: ‘password’,
 ‘client_id’: app_id,
 ‘client_secret’: client_secret,
 ‘resource’: ‘https://graph.microsoft.com',
 ‘scope’:’https://graph.microsoft.com',
 ‘username’:’john.doe@companyxxx.com’, #Account with no 2MFA
 ‘password’:’Happy2020’,
}
token_r = requests.post(token_url, data=token_data)
token = token_r.json().get(‘access_token’)
