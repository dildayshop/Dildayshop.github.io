# Dildayshop.github.io
Website for Coastal Projects LLC
mkdir coastal-projects-site
cd coastal-projects-site
{
  "name": "coastal-projects-site",
  "version": "1.0.0",
  "description": "Website for Coastal Projects LLC, home remodeling & design in New Bern, NC.",
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview"
  },
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0",
    "react-router-dom": "^6.23.0"
  },
  "devDependencies": {
    "vite": "^5.0.0",
    "@vitejs/plugin-react": "^4.0.0"
  }
}
import React, { useState } from 'react';

export default function Contact() {
  const [form, setForm] = useState({name: '', email: '', message: ''});
  const [submitted, setSubmitted] = useState(false);

  const handleChange = e => {
    setForm({...form, [e.target.name]: e.target.value});
  };

  const handleSubmit = e => {
    e.preventDefault();
    setSubmitted(true);
    // In production, connect to an email service or backend.
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
