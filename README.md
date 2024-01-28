# ChatGPT Lite plan

## Quickstart

### Prerequisites

- Python >= 3.8
- A Fly.io account

### Step 1: Install the Fly CLI

Install the Fly CLI to deploy apps using command lines.

For macOS:

```shell
brew install flyctl
```

For other operating systems, follow the [installation guide](https://fly.io/docs/getting-started/installing-flyctl/).

### Step 2: Login to Fly

Sign up and log in to Fly.

```shell
flyctl auth signup
flyctl auth login
```

### Step 3: Run Chainlit App Locally

Test your app locally before deploying.

Clone this repository:

```shell
git clone https://github.com/jerrybabah/chatgpt-lite-plan.git chatgpt-lite-plan
cd chatgpt-lite-plan
```

Set .env:

```shell
touch .env

# copy and paste .env.example to .env
# input your data
```

Run your app:

```shell
chainlit run app.py
```

### Step 5: Create Fly Project

Set up a payment method on Fly.io (no charge for the free plan).

Then, create your Fly project:

```shell
flyctl launch
```

Answer "No" to all prompts during setup.

### Step 6: Deploy

Deploy your app:

```shell
flyctl deploy
```

After deployment, set the app instance count to 1:

```shell
flyctl scale count 1
```

This is necessary because Fly.io doesn't support sticky WebSocket sessions by default.

Visit your app at the provided hostname from the `flyctl launch` output.
