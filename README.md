Bolt Setup Instructions
------------------------
*Follow these steps to set up and run Bolt.DIY on Colab:*
1. **Install pnpm:** !npm install -g pnpm
This command installs the pnpm package manager globally.

2. **Clone the Bolt.DIY repository:** !git clone -b stable https://github.com/stackblitz-labs/bolt.diy.git
This command clones the Bolt.DIY repository from GitHub, specifically the stable branch, into a directory named bolt.diy.

3. **Navigate to the Bolt.DIY directory:** %cd bolt.diy
This command changes your current directory to the bolt.diy directory, which was created in the previous step.

4. **Install project dependencies:** !pnpm install
This command installs the required dependencies for the Bolt.DIY project, as specified in its package.json file.

5. **Set up ngrok (for external access):**
Obtain ngrok authtoken:  
You will need an ngrok authtoken to create a public URL for your local server.
   * If you don't have one, sign up for a free account at [Ngrok](https://ngrok.com/) and get your authtoken from the dashboard.
   * enter the TOKEN in script where it asks "YOUR_TOKEN". and run the script

```
from pyngrok import ngrok
#Replace 'YOUR_AUTHTOKEN' with your actual ngrok authtoken
ngrok.set_auth_token("YOUR_AUTHTOKEN")

#Open a tunnel to port 5173 (where your Vite dev server is running)
tunnel = ngrok.connect(5173)

#Print the public URL of the tunnel
print("Public URL:", tunnel.public_url)

#This will give you a public https:// URL that you can open in your mobile browser,
#and it will forward all the traffic to "localhost:5173" inside your Colab environment.
```

6. **Start the development server:** !pnpm run dev
This command starts the Bolt.DIY development server.  
It will typically start a local web server (often using Vite) that you can access in your browser.

***Example Colab Link: [Bolt Colab](https://colab.research.google.com/drive/1oJDErM2YW8-zTGgXddR1l16NoXveStS3#scrollTo=yX_Bl9-0Wata)***
