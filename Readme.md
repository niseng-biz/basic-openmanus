# How to use

## geminiを使う場合の設定（初期設定）


ターミナルからこのコードをたたいて、config.tomlを作成（example.tomlからコピー）します。

```bash
cp OpenManus/config/config.example.toml OpenManus/config/config.toml
```

config.tomlの以下２か所を書き換えます。

```bash
[llm]
model = "gemini-2.5-flash"
base_url = "https://generativelanguage.googleapis.com/v1beta"
api_key = "GeminiのAPIキーを入れる"
max_tokens = 8192
temperature = 0.0


# Optional configuration for specific LLM models
[llm.vision]
model = "gemini-2.5-flash"
base_url = "https://generativelanguage.googleapis.com/v1beta/openai/"
api_key = "GeminiのAPIキーを入れる"


# Optional Runflow configuration
# Your can add additional agents into run-flow workflow to solve different-type tasks.
[runflow]
use_data_analysis_agent = false     # The Data Analysi Agent to solve various data analysis tasks

# Run browser in headless mode for WSL
headless = false # GUIを表示
# Disable browser security features for WSL compatibility
disable_security = true
# Extra arguments for WSL browser
extra_chromium_args = [
    "--no-sandbox",
    "--disable-gpu",
    "--disable-dev-shm-usage",
    "--disable-setuid-sandbox",
    "--remote-debugging-port=9222",
    "--remote-debugging-address=0.0.0.0",
]
# Connect to a browser instance via CDP
cdp_url = "http://localhost:9222"

```


## いつもの起動
ターミナルから下記を入力してOpenManusが入っているvenvを起動します。
```bash
cd OpenManus
. .venv/bin/activate 
```

最後に下記コマンドでManusが立ちあがります！
（公式リポジトリ通りmain.pyを使うと、会話ができません。）
```bash
python run_flow.py
```

終了はctrl+Cを２回押してください。
