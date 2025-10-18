# Travel & Lifestyle Sales Funnel

A modern, responsive landing page for capturing leads interested in travel and lifestyle opportunities. Built with HTML, CSS, JavaScript, and Supabase for backend functionality.

## 🚀 Quick Start

### Prerequisites
- Node.js (version 14 or higher)
- npm (comes with Node.js)
- A Supabase account (free)

### Installation

1. **Clone or download this repository**
   ```bash
   git clone https://github.com/Smeltzer43/sales-funnel.git
   cd sales-funnel
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up Supabase** (see [SUPABASE_SETUP.md](./SUPABASE_SETUP.md) for detailed instructions)
   - Create a Supabase project
   - Get your URL and API key
   - Update the credentials in `index.html` (lines 729-730)

4. **Start the development server**
   ```bash
   npm run dev
   ```
   This will open your browser to `http://localhost:3000`

## 📁 Project Structure

```
sales-funnel/
├── index.html              # Main landing page
├── assets/                 # Images and media files
│   ├── Hero.png
│   ├── family.png
│   └── ... (other assets)
├── package.json           # Node.js dependencies
├── SUPABASE_SETUP.md      # Detailed Supabase setup guide
└── README.md              # This file
```

## 🛠 Available Scripts

- `npm run dev` - Start development server (port 3000)
- `npm start` - Same as dev (port 3000)
- `npm run serve` - Start production server (port 8080)
- `npm run build` - No build needed (static site)

## 🎯 Features

- **Responsive Design** - Works on desktop, tablet, and mobile
- **Lead Capture Forms** - Multiple popup forms throughout the page
- **Supabase Integration** - Real-time database storage
- **Modern UI/UX** - Clean, professional design
- **Fast Loading** - Optimized images and code

## 🔧 Configuration

### Supabase Setup
1. Follow the detailed guide in [SUPABASE_SETUP.md](./SUPABASE_SETUP.md)
2. Update these values in `index.html`:
   ```javascript
   const SUPABASE_URL = 'YOUR_SUPABASE_URL';
   const SUPABASE_ANON_KEY = 'YOUR_SUPABASE_ANON_KEY';
   ```

### Customization
- **Colors**: Update CSS variables in the `<style>` section
- **Content**: Modify text and images in the HTML
- **Forms**: Adjust form fields and validation in JavaScript
- **Styling**: Update CSS classes and styles

## 📊 Lead Management

Leads are automatically stored in your Supabase database with:
- First name, last name, email
- Source tracking (which form was used)
- Timestamp
- Status tracking

## 🚀 Deployment

### Option 1: Static Hosting (Recommended)
- **Netlify**: Drag and drop your project folder
- **Vercel**: Connect your GitHub repository
- **GitHub Pages**: Push to a GitHub repository

### Option 2: Traditional Web Hosting
- Upload all files to your web server
- Ensure your Supabase credentials are updated
- Test the forms work correctly

## 🔒 Security Notes

- The Supabase anon key is safe to use in frontend code
- Row Level Security (RLS) is enabled by default
- All form submissions are validated client-side and server-side

## 🐛 Troubleshooting

### Common Issues

1. **"Module not found" errors**
   ```bash
   npm install
   ```

2. **Supabase connection errors**
   - Check your URL and API key
   - Verify your Supabase project is active
   - Check browser console for specific errors

3. **Forms not submitting**
   - Ensure Supabase credentials are correct
   - Check browser console for JavaScript errors
   - Verify your database table exists

4. **Styling issues**
   - Clear browser cache
   - Check for CSS conflicts
   - Verify all asset paths are correct

## 📈 Analytics & Tracking

Consider adding:
- Google Analytics
- Facebook Pixel
- Custom event tracking
- A/B testing for different versions

## 🤝 Support

For issues or questions:
1. Check the troubleshooting section above
2. Review the Supabase setup guide
3. Check browser console for errors
4. Verify all dependencies are installed

## 📝 License

MIT License - feel free to use this project for your own purposes.

---

**Ready to capture leads?** Follow the setup instructions above and start collecting leads in minutes! 🎉
