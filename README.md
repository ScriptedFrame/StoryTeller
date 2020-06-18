# StoryTeller
This project was sparked from a love of rpg, visual novels, choice adventures, and more.
The idea behind the project is for an online editor and play system for users across the world to build their stories, decision trees, inventories, and more.

###### Consider supporting the primary developer from our team on this project
[![ko-fi](https://www.ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/B0B11U1AM)

## Todo
- [ ] User system (used for creating and saving last point in story)
- [ ] Story storage system (having to decide between MongoDB, MySQL, or JSON), will discuss the pros and cons
    - MySQL
        - 👍 Comes with just about all webhosts for free.
        - 👍 Extremely common, comes free with most webhosts.
        - 👎 However becomes slow with large databases.
    - MongoDB
        - 👍 Relatively faster than MySQL when handling large databases.
        - 👎 You need to pay a company or own a VPS to host a MongoDB instance, less cost efficient
    - JSON File storage
        - 👍 Faster fetch times usually than MongoDB and MySQL
        - 👎 Would have to be chunked or split into each option for speed and performance consideration
        - 👎 Less easy to make a system to fetch from multiple storage centers
- [ ] Possible private story mode (allowing people to make private stories [such as for Patreon(s) and other such])

#### Need help from the community
1. Best license?
    - This is open source, help is accepted.
    - I don't want people to out right take **our** progress and resell it.
        - This is a community project after all!
2. APK and EXE generator?
    - People of course will want to monetize their stories and such, and we're for that! So the issues are the following;
        - Making the stories have an "offline" system, possible JSON storage? These stories would likely not have an inventory system, as it would take more effort than is needed.
    - JSON is the most obvious route, however we need to decide if it should be key based, or tree based examples in "Expanded-1"
    
------
# Expanded-1
- Keys
```json
{
  "1": {
    "text": "You see a knife in front of the sleeping guard...",
    "background-img": "base64",
    "options": [["You pick up the knife","1.1"],["You sneak by","1.2"],["You go back to your cell","1.3"]]
  },
  "1.1": {
    "text": "etc",
    "background-img": "base64",
    "options": [["etc","0.0"]]
  }
}
```
- Tree
```json
{
  "story": {
    "text": "You see a knife in front of the sleeping guard...",
    "background-img": "bas64",
    "options": [
      {
        "desc": "You pick up the knife",
        "text": "You picked up the knife, woke up the guard, and threatened them to let you out",
        "options": ["/*repeat again and again as needed*/"]
      }
    ]
  }
}
```