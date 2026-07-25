# Your Gelbooru Favorite's Character Leaderboard
<img width="2848" height="811" alt="Github - Banner" src="https://github.com/user-attachments/assets/d9a23fd4-f30a-4644-9c1c-449675520f57"/>

Process your Gelbooru favorite's characters locally by count for a spreadsheet and a GUI page with pictures to see pitted in a leaderboard.

Inspired by Sankaku's Complex now discontinued favorite characters stat that used to be shown on your profile.

This script runs locally with your API key saved locally and not sent to any third party websites including your results.

# Requirements:

- Python 3.8+
- Gelbooru account with favorites
- requests (>=2.25.1)
- pandas (>=1.3.0)
- openpyxl (>=3.0.7)
- Pillow (>=9.0.0)

Tested in Windows 10.

### Install via CMD:

> pip install requests pandas openpyxl Pillow

## To use:

1. Just download the release and extract.

2. Go to account options to fetch the API Access Credentials key at the bottom: https://gelbooru.com/index.php?page=account&s=options

    1. It'll look like &api_key=INSERTLONGAPIKEYHERE&user_id=NUMBERS

3. Then just run 'Fetch_favorites_RUN.bat' or run 'run_retrospective.py' itself manually in CMD.

4. You'll be prompted for the first time if you haven't entered your API key before for that.

5. Follow instructions from there, note that the long processing time, especially if you have +1k favorited posts, is to make sure you aren't overbearing Gelbooru with API calls. For example my account with 12.2k favorited posts took 54 minutes to process altogether alongside the GUI page.

6. When done, it'll auto-launch "favorite_characters.html" in your default browser, else you can manually open it up anytime afterwards if you didn't set to auto-delete.

# More pics:

<img width="1902" height="1047" alt="2" src="https://github.com/user-attachments/assets/faffd9c8-5316-4a02-b85f-61195bca882c" />

<img width="1895" height="1077" alt="3" src="https://github.com/user-attachments/assets/ca6f8068-06ff-44e6-be4e-a8e74b00344f" />

# How and what the program does:

This program works by paginating through your entire Gelbooru favorites list to build a dictionary of every tag. To handle collections of any size efficiently, it uses dynamic thresholding to filter out rare tags before using a multithreaded connection pool to verify which tags are actually characters without triggering API rate limits. Once your top characters are identified and put into a spreadsheet, the script fetches their top-scoring artwork as pictures for the GUI page and builds accordingly.

## Other remarks

This script was done using Google Gemini Pro as I'm a very novice programmer, but from testing with my account with 12.2k favorited posts it worked and got 506 characters charted.
