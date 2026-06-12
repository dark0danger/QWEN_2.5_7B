# API Reference: Codeforces Tutor AI Engine

This document outlines the API endpoint available for interacting with the fine-tuned Qwen2.5-Coder-7B model server. The server is exposed publicly via Ngrok on port 5000.

## Base URL
`http://<your-ngrok-public-url>.ngrok-free.app`

---

## Codeforces Generation Endpoint

### `POST /generate`
Generates either a short programming hint or a full Python solution for a given Codeforces problem statement.

### Headers
| Header | Value | Description |
| :--- | :--- | :--- |
| `Content-Type` | `application/json` | Required |

### Request Body (JSON)

The endpoint accepts two different formatting modes: **Structured Fields** (highly recommended for RAG systems) or **Raw Input String**.

#### Option A: Structured Fields (Recommended)
Pass the separated metadata components directly. The backend automatically constructs the optimal instruction prompt.

| Field | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| `problem` | `string` | Yes | The text or description of the Codeforces problem. |
| `rating` | `string/int` | No | The official Codeforces difficulty rating (e.g., `"800"`, `"1500"`). Defaults to `"Unknown"`. |
| `topics` | `string` | No | Comma-separated problem tags (e.g., `"dp, math, greedy"`). Defaults to `"Unknown"`. |
| `mode` | `string` | No | Options: `"hint"` (returns a 1-2 sentence tip) or `"solution"` (returns full Python code). Defaults to `"hint"`. |

**Example Payload (Hint Mode):**
```json
{
  "problem": "A watermelon can be divided into two even parts...",
  "rating": "800",
  "topics": "math, brute force",
  "mode": "hint"
}
