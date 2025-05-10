# Meeting Room Booking AI Agent

## Overview
This project is an AI Agent designed to simplify meeting room bookings for entrepreneurs. It interacts with users through a conversational interface, collects booking details (date, time, room, name), validates them, and confirms reservations in JSON format. The system is efficient, user-friendly, and built with modern AI technologies.

## Objective
The AI Agent manages bookings for four meeting rooms:
- **Room A**: Advanced audio-visual technology.
- **Room B**: Spacious for large presentations.
- **Room C**: Compact for private meetings.
- **Room D**: Scenic view with a comfortable atmosphere.

It ensures all required details are provided before confirming a booking.

## Demonstration Video
The project is demonstrated through a video showcasing a live interaction with the AI Agent. The video illustrates a successful booking process, highlighting the agent’s conversational abilities, validation logic, and ease of use. It is the primary component for evaluation.

📽️ **Watch the Demonstration Video**:  [click here to watch video ](https://drive.google.com/file/d/1i-jz7cBBdv4YbNbAlCu8OsD8WuZihsw3/view?usp=sharing)  


## Technologies Used
The following technologies were selected for their reliability and suitability:

### 1. LangChain
- **Purpose**: Manages conversational workflows and integrates with the language model.
- **Why**: Simplifies building context-aware AI agents by handling message history and prompts.
- **How It’s Used**: Guides the booking process, prompting for missing details and validating inputs.
- **Example**:
  ```python
  from langchain_core.messages import SystemMessage, HumanMessage
  messages = [
      SystemMessage(content="You are a booking assistant. Collect date, time, room, name."),
      HumanMessage(content="Book Room C.")
  ]
  # Agent requests missing details like date and time.
  ```

### 2. Streamlit
- **Purpose**: Provides a web-based interface for user interaction.
- **Why**: Enables rapid development of interactive web apps.
- **How It’s Used**: Displays the chat interface and booking confirmations.
- **Example**:
  ```python
  import streamlit as st
  st.title("Room Booking Assistant")
  user_input = st.chat_input("Enter your request:")
  if user_input:
      st.write("Processing...")
  ```

### 3. Groq API
- **Purpose**: Powers the conversational intelligence.
- **Why**: Offers fast language model inference for real-time responses.
- **How It’s Used**: Processes user inputs and generates responses.
- **Example**:
  ```python
  from langchain_groq import ChatGroq
  client = ChatGroq(api_key="your-api-key", model_name="compound-beta-mini")
  response = client.invoke("Book Room B for tomorrow.")
  ```

### 4. Python
- **Purpose**: Core programming language.
- **Why**: Supports AI and web development with a rich ecosystem.
- **How It’s Used**: Handles backend logic, session state, and JSON output.

## System Architecture
The AI Agent follows a modular workflow, as shown in the video:
- **Input Processing**: Extracts booking details.
- **Validation**: Ensures all fields are provided.
- **Output**: Generates JSON confirmations.
- **Interface**: Manages user interactions via Streamlit.

### Data Flow
```
[User Input] → [Streamlit UI] → [LangChain + Groq API] → [Validation] → [JSON Output] → [Confirmation]
```

## Implementation Highlights
- **Conversational Flow**: Uses a system prompt to collect and validate details, as seen in the video.
- **Session Management**: Tracks conversation and booking history.
- **Error Handling**: Prompts users to correct invalid inputs.
- **Output Format**:
  ```json
  {
    "date": "2025-05-20",
    "time": "10:00",
    "name": "Sarah Smith",
    "room": "B"
  }
  ```

## Why an AI Agent?
- **Autonomy**: Processes requests independently.
- **Interactivity**: Engages users naturally, as demonstrated.
- **Task-Specificity**: Tailored for room booking.

## Challenges and Solutions
1. **Challenge**: Natural conversation flow.
   - **Solution**: Designed a precise prompt, shown in the video.
2. **Challenge**: Responsive UI.
   - **Solution**: Used Streamlit’s streaming for real-time updates.
3. **Challenge**: Secure configuration.
   - **Solution**: Managed API keys via `dotenv`.

## Sample Interaction (From Video)
**User**: "Book Room B for May 20, 2025, at 10 AM under Sarah Smith."  
**Agent**: "Booking confirmed."  
**Output**:
```json
{
  "date": "2025-05-20",
  "time": "10:00",
  "name": "Sarah Smith",
  "room": "B"
}
```

## Source Code Status
The source code is not open-source, as this project is a proprietary effort for a paid engagement. Only illustrative code snippets are provided to demonstrate the technical approach. The demonstration video fully showcases the system’s functionality for evaluation.

## Future Enhancements
- Database for persistent booking storage.
- Calendar API for availability checks.
- Multilingual support.

## Evaluation Instructions
The demonstration video is the primary evidence of the AI Agent’s capabilities, supported by this README and illustrative snippets. The source code is proprietary and not open-source due to its commercial nature. For further details or a live demo, contact yahyamahroof35@gmail.com.
