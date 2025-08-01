<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <title>Coastal Projects LLC</title>
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <!-- Favicon (optional) -->
    <link rel="icon" href="data:," />
    <style>
      body {
        font-family: 'Segoe UI', Arial, sans-serif;
        margin: 0;
        background: #f5f7fa;
        color: #223;
      }
      .navbar {
        display: flex;
        justify-content: space-between;
        align-items: center;
        background: #2b5d7b;
        padding: 1rem 2rem;
        color: #fff;
      }
      .navbar .logo {
        font-weight: bold;
        font-size: 1.3rem;
      }
      .navbar ul {
        list-style: none;
        display: flex;
        gap: 1.5rem;
        margin: 0;
        padding: 0;
      }
      .navbar a {
        color: #fff;
        text-decoration: none;
      }
      .navbar a:hover {
        text-decoration: underline;
      }
      .hero {
        background: linear-gradient(120deg, #6ec1e4 0%, #88d3ce 100%);
        color: #fff;
        padding: 3rem 2rem 2rem 2rem;
        text-align: center;
      }
      .hero h1 {
        font-size: 2.5rem;
        margin-bottom: 0.5rem;
      }
      .cta {
        display: inline-block;
        margin-top: 1.5rem;
        background: #2b5d7b;
        color: #fff;
        padding: 0.75rem 2rem;
        border-radius: 30px;
        font-weight: bold;
        text-decoration: none;
      }
      .cta:hover {
        background: #234b63;
      }
      .about, .services-list, .contact-form, .contact-info {
        margin: 2rem auto;
        max-width: 600px;
        background: #fff;
        border-radius: 8px;
        padding: 2rem;
        box-shadow: 0 2px 8px rgba(0,0,0,0.05);
      }
      .services-list {
        list-style: disc inside;
        padding-left: 1rem;
      }
      .contact-form label {
        display: block;
        margin-bottom: 1rem;
      }
      .contact-form input, 
      .contact-form textarea {
        width: 100%;
        margin-top: 0.25rem;
        padding: 0.5rem;
        border: 1px solid #bbb;
        border-radius: 4px;
      }
      .contact-form button {
        background: #2b5d7b;
        color: #fff;
        padding: 0.7rem 1.5rem;
        border: none;
        border-radius: 30px;
        margin-top: 1rem;
        cursor: pointer;
      }
      .contact-form button:hover {
        background: #234b63;
      }
      footer {
        text-align: center;
        padding: 2rem 0 1rem 0;
        color: #555;
        background: #e5ecf2;
        margin-top: 2rem;
      }
    </style>
  </head>
  <body>
    <div id="root"></div>
    <!-- React and Babel CDN -->
    <script src="https://unpkg.com/react@18/umd/react.development.js" crossorigin></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js" crossorigin></script>
    <script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
    <!-- Your React code -->
    <script type="text/babel">

      function Navbar({ page, setPage }) {
        return (
          <nav className="navbar">
            <div className="logo">Coastal Projects LLC</div>
            <ul>
              <li><a href="#home" onClick={() => setPage('home')}>Home</a></li>
              <li><a href="#services" onClick={() => setPage('services')}>Services</a></li>
              <li><a href="#gallery" onClick={() => setPage('gallery')}>Gallery</a></li>
              <li><a href="#contact" onClick={() => setPage('contact')}>Contact</a></li>
            </ul>
          </nav>
        );
      }

      function Home() {
        return (
          <section className="home">
            <div className="hero">
              <h1>Coastal Projects LLC</h1>
              <p>Home Remodeling & Design · New Bern, NC</p>
              <a href="#contact" className="cta">Get a Free Estimate</a>
            </div>
            <div className="about">
              <h2>About Us</h2>
              <p>
                Coastal Projects LLC is a locally owned and family owned business, proudly serving New Bern, NC since 2022. We specialize in home remodeling and design. Whether you’re looking to update your kitchen, renovate a bathroom, or reimagine your living space, our team is dedicated to bringing your vision to life with quality craftsmanship and attention to detail.
              </p>
            </div>
          </section>
        );
      }

      function Services() {
        return (
          <section>
            <h2>Our Services</h2>
            <ul className="services-list">
              <li>Kitchen Remodeling</li>
              <li>Bathroom Renovation</li>
              <li>Whole-Home Remodeling</li>
              <li>Interior & Exterior Design</li>
              <li>Flooring & Tiling</li>
              <li>Custom Carpentry</li>
              <li>Decks & Outdoor Living Spaces</li>
            </ul>
            <p>
              Have a unique project in mind? <a href="#contact">Contact us</a> to discuss your ideas!
            </p>
          </section>
        );
      }

      function Gallery() {
        return (
          <section>
            <h2>Gallery</h2>
            <p>Check back soon to see photos of our latest projects!</p>
          </section>
        );
      }

      function Contact() {
        const [form, setForm] = React.useState({name: '', email: '', message: ''});
        const [submitted, setSubmitted] = React.useState(false);

        const handleChange = e => {
          setForm({...form, [e.target.name]: e.target.value});
        };

        const handleSubmit = e => {
          e.preventDefault();
          setSubmitted(true);
        };

        return (
          <section>
            <h2>Contact Us</h2>
            {submitted ? (
              <p>Thank you for reaching out! We'll get back to you soon.</p>
            ) : (
              <form className="contact-form" onSubmit={handleSubmit}>
                <label>
                  Name
                  <input name="name" value={form.name} onChange={handleChange} required />
                </label>
                <label>
                  Email
                  <input name="email" type="email" value={form.email} onChange={handleChange} required />
                </label>
                <label>
                  Message
                  <textarea name="message" value={form.message} onChange={handleChange} required />
                </label>
                <button type="submit">Send Message</button>
              </form>
            )}
            <div className="contact-info">
              <p><strong>Coastal Projects LLC</strong></p>
              <p>New Bern, NC</p>
              <p>Email: <a href="mailto:dildayshop@gmail.com">dildayshop@gmail.com</a></p>
            </div>
          </section>
        );
      }

      function App() {
        const [page, setPage] = React.useState('home');

        let Content;
        switch (page) {
          case 'services': Content = <Services />; break;
          case 'gallery': Content = <Gallery />; break;
          case 'contact': Content = <Contact />; break;
          default: Content = <Home />; break;
        }

        return (
          <>
            <Navbar page={page} setPage={setPage} />
            <main>
              {Content}
            </main>
            <footer>
              © {new Date().getFullYear()} Coastal Projects LLC · New Bern, NC
            </footer>
          </>
        );
      }

      ReactDOM.createRoot(document.getElementById('root')).render(<App />);
    </script>
  </body>
</html>
