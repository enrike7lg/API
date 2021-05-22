<script>
	import Router from 'svelte-spa-router';
	import NotFound from './NotFound.svelte' ;  
  import Inicio from './Inicio.svelte'

  //Imports para APIs
  import SchoolAPI from './schoolGUI/childrenOutSchoolTable.svelte'
  import EditSchool from './schoolGUI/editSchool.svelte'

  //Imports para analytics
	import AnalyticsSchool from "./analytics/school/schoolAnalytics.svelte";

	import {Collapse,Jumbotron,Navbar,NavbarToggler,NavbarBrand,Nav,NavItem,NavLink,Dropdown,UncontrolledDropdown,DropdownToggle,DropdownMenu,DropdownItem} from 'sveltestrap';
  
    let isOpen=false;
    
    const routes = {
      "/": Inicio,
      "/children-out-school": SchoolAPI,
      "/children-out-school/:country/:year":EditSchool,
      "/analytics/children-out-school": AnalyticsSchool,
		  '*': NotFound,
    };
</script>

<main>
    <body>
      <Jumbotron style="background-color:mediumpurple;"class="p-3" >
        <h1 style="text-align:center; " class="display-4">SOS2021-24 API ABANDONO ESCOLAR</h1>
      </Jumbotron>
        <Navbar color="dark" dark expand = "md" >
            <NavbarBrand href="#/">SOS2021-24</NavbarBrand>
            <Nav navbar >
              <NavItem>
                <NavLink href="#/info">Info</NavLink>
              </NavItem>
              <NavItem>
                <NavLink href="#/children-out-school">Abandono escolar</NavLink>
              </NavItem>
              <NavItem>
                <NavLink href="#/analytics/children-out-school">Analítica</NavLink>
              </NavItem>
            </Nav>
        </Navbar>
    </body>

    <Router {routes}> </Router>
</main>