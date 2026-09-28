export default function Footer() {
  return <footer style={{background: '#333', color: 'white', textAlign: 'center', padding: '10px'}}>© 2026 House Rent App</footer>
}






import { Outlet } from 'react-router-dom'
import Navbar from './Navbar'
import Footer from './Footer'

export default function Layout() {
  return (
    <div>
      <Navbar /> {/* ✅ NavLink with active styling */}
      <main style={{minHeight: '80vh', padding: '20px'}}>
        <Outlet /> {/* Nested pages will render here */}
      </main>
      <Footer />
    </div>
  )
}
