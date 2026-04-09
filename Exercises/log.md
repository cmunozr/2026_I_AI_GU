Log

Running nohup on remote server, local development on Windows and experimentation on Colab. Use a Runtime Environment Manager coupled environment variables to distinguish between "Local Windows" and "Remote Ubuntu Server."

´´´
import os
import sys
import platform

def detect_environment():
    if 'google.colab' in sys.modules:
        return "COLAB"  
    os_name = platform.system().upper() # Returns 'WINDOWS', 'LINUX', or 'DARWIN' (Mac)
    
    # Need of a custom variable in Remote Conda env
    if os_name == "LINUX" and os.environ.get('IS_REMOTE_SERVER') == 'true':
        return "REMOTE_LINUX"
    
    return f"LOCAL_{os_name}"

# Initialize Environment
ENV = detect_environment()
print(f"Current Environment: {ENV}")

# --- Set Paths and Configuration Based on Environment ---
if ENV == "COLAB":
    DATA_PATH = "/content/drive/MyDrive/PhD/data"
    # !pip install -q scikit-learn tensorflow  # Silent install for Colab
elif ENV == "REMOTE_LINUX":
    DATA_PATH = "/home/carlos/project/data"
    BATCH_SIZE = 128  # Use larger batch size for your NVIDIA GPU
elif "LOCAL_WINDOWS" in ENV:
    DATA_PATH = "C:/Users/Carlos/PhD/data"
    BATCH_SIZE = 16   # Smaller batch for local testing
´´´

Set a specific environment variable in the Remote Conda Environment. On Ubuntu Server, activate conda env:

´´´
conda activate env_name
´´´

Set the variable permanent for that env:

´´´
conda env config vars set IS_REMOTE_SERVER=true
´´´

Restart the env: (Deactivate and reactivate).

Non-Interactive Execution: When running as a script on Ubuntu, I can use nbconvert so no need of manually converting .ipynb to .py:

´´´
nohup jupyter nbconvert --to notebook --execute my_analysis.ipynb --output my_results.ipynb &
´´´

