# streamlit-chatgpt-ui as MyChatGPT_workspace 
Go for the desktop/workspace ChatGPT-like UI built with Streamlit.
![gtp_desktop](./images/gpt_workspace.png)
### Environment setup
- .venv (Python 3.8.10)
    ```
    $ python3 -m venv .venv
    $ source .venv/bin/activate
    $ pip install -r requirements.txt
    ```
- .env definition
  ```
  OPENAI_API_KEY = "your OpenAI key"
  ```
    * option `CHATGPT_LOGO`, if set a logo by SVG format, will see useful ChatGPT-like output format  
    (its the markdown on streamlit). otherwise will see avatar as chat format as default.
      ```
      CHATGPT_LOGO = "your logo"
      ```
### Usage
- Start stremlit
    ```
    $ cd src
    $ streamlit run app_workspace.py
    ```

    * option `-- -l ja` is system language in japanese. (default:en)
      ```
      e.g.
      $ streamlit run app_workspace.py -- -l ja
      ```
    * option `-- -gstyle "GPT avatar style" -gname "GPT avatar name" -ustyle "Your avatar style" -uname "Your avatar name"`
      is avatar style and seed as name. but, GPT avatar's option ignore, if set CHATGPT_LOGO 
      (Avatar could be work in ref. [https://www.dicebear.com](https://www.dicebear.com/playground) with confirmed avatar in avatar.yaml file, add please.)
      ```
      e.g.
      $ streamlit run app_workspace.py -- -gstyle bottts -gname Gizmo -ustyle thumbs -uname Cleo
      ``` 

- on Docker
    ```
    ($ sudo service docker start), if WSL2
     $ docker-compose up
       └→ http://localhost:8501/
    ```

- Streamlit sidebar menu
  1. Preset menu:
    a: Choose a model
    b: Upload .csv file
  2. Autopilot menu:
    a: Autopilot .csv data continuous for loop
    b: Reproduction GPT conversation on saved .csv data
  3. Initialize menu:
    a: Clear Conversation with reset Total cost
    b: set GPT icon
    c: (API) Key visible and edit
    d: Role visible and edit
  4. Log menu:
    a: Total cost of this conversation
    b: Show session_state
    c: Download data(Conversation) as .csv file


