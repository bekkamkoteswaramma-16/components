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





import { NavLink } from 'react-router-dom' // ✅ NavLink for active

const navLinks = [ // ✅ Dynamic Links using .map()
  {name: 'Home', path: '/'},
  {name: 'About', path: '/about'},
  {name: 'Dashboard', path: '/dashboard'},
  {name: 'Login', path: '/login'}
]

export default function Navbar() {
  return (
    <nav style={{background: '#333', padding: '10px', display: 'flex', gap: '20px'}}>
      {navLinks.map(link => (
        <NavLink 
          key={link.path}
          to={link.path}
          style={({isActive}) => ({ // ✅ Active styling
            color: isActive ? 'yellow' : 'white',
            textDecoration: 'none'
          })}
        >
          {link.name}
        </NavLink>
      ))}
    </nav>
  )
}
