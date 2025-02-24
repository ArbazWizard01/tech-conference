# Tech Conference 2025 - EmptyCup

Welcome to the official repository for the **Tech Conference 2025** website. This project is built using **SvelteKit** and showcases details about the conference, including **speakers, schedule, sponsors, and more**.

## 🚀 Features
- **Dynamic Speaker List**: Displays featured speakers and their details.
- **Schedule Management**: Fetches and displays the event schedule.
- **Sponsors Section**: Showcases sponsor logos dynamically.
- **Interactive UI**: Engaging design with animations and transitions.
- **Responsive Design**: Fully optimized for mobile, tablet, and desktop.
- **Easy Navigation**: Smooth scrolling and intuitive navigation bar.

## 🛠 Installation & Setup

To set up the project locally, follow these steps:

### Prerequisites
Ensure you have the following installed:
- **Node.js** (Latest LTS version recommended)
- **npm** or **pnpm**

### Steps
1. **Clone the Repository**
   ```sh
   git clone https://github.com/yourusername/tech-conference.git
   cd tech-conference
   ```

2. **Install Dependencies**
   ```sh
   npm install  # or pnpm install
   ```

3. **Run the Development Server**
   ```sh
   npm run dev
   ```
   This will start a local server at `http://localhost:5173/`.

4. **Build for Production**
   ```sh
   npm run build
   ```

5. **Preview the Production Build**
   ```sh
   npm run preview
   ```

## 📁 Project Structure
```
tech-conference/
│── src/
│   ├── lib/
│   │   ├── About.svelte
│   │   ├── Contact.svelte
│   │   ├── index.js
│   │   ├── Navbar.svelte
│   │   ├── Schedule.svelte
│   │   ├── Sidebar.svelte
│   │   ├── Speaker.svelte
│   │   ├── Sponsor.svelte
│   ├── routes/
│   │   ├── about/
│   │   │   ├── +page.svelte
│   │   ├── contact/
│   │   │   ├── +page.svelte
│   │   ├── schedule/
│   │   │   ├── +page.svelte
│   │   ├── speakers/
│   │   │   ├── +page.svelte
│   │   ├── sponsors/
│   │   │   ├── +page.svelte
│   │   │   ├── +layout.svelte
│── static/
│── .gitignore
│── .npmrc
│── .prettierignore
│── app.html
```


