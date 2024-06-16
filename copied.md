import React, { useEffect }from 'react';
import {BrowserRouter, Routes, Route } from 'react-router-dom';
import { FiSettings } from 'react-icons/fi';
import { TooltipComponent} from '@syncfusion/ej2-react-popups';

import {Navbar, Footer, Sidebar, ThemeSettings} from './components';

import {Ecommerce, Orders, Calendar, Employees,Customers,Editor, Stacked, Pyramid, Customer, Kanban, Area, Bar, Pie, Financial,ColorPicker, ColorMapping, Line} from './pages';


import  './App.css';
import { BiSidebar } from 'react-icons/bi';



const App = () => {

const activeMenu = true;

  return (

    <div>
      <BrowserRouter>
      <div className="flex relative dark:bg-main-dark-bg">  
        <div className="fixed right-4 bottom-4" style={{ zIndex: '1000'}}>
        <TooltipComponent content="settings" position='Top'>
            <button type='button' className='text-3xl p3 hover:drop-shadow-xl hover:bg-light-gray text-white'
            style={{ background:'blue', borderRadius:'50%' }}>
                <FiSettings/>
            </button>
        </TooltipComponent>
        </div>

        {activeMenu ?(
            <div className='w-72 fixed sidebar dark:bg-secondary-dark-bg
            bg-white'> 
            <Sidebar />
            </div>
        ): (
            <div className='w-0 bg-secondary-dark-bg'>
                            <Sidebar />

            </div>
        )}
        <div className={
            `dark:bg-main-bg bg-main-bg min-h-screen w-full  ${activeMenu ? 'md:ml-72' : 'flex-2'}`  
        }>

            <div className='fixed md:static bg-main-bg dark:bg-main-dark-bg
            navbar w-4'>
                            <Navbar />


            </div>
        </div>


        <div>
            <Routes>
                {/*Dashboard}*/}
                <Route path='/' element={<Ecommerce/>} />
                <Route path='/ecommerce' element={<Ecommerce/>} />

                {/*Pages}*/}
                <Route path='/orders' element={<Orders/>  } />              
                <Route path='/employes' element= {<Employees/>}/>         
                <Route path='/customerss' element={<Customers/>} />

                    {/*Apps}*/}
                <Route path='/kanban' element={<Kanban/> } />             
                 <Route path='/editor' element= {<Editor/>} />            
                  <Route path='/calendar' element={<Calendar/>} />
              <Route path='/color-picker' element={<ColorPicker/>} />

                {/*charts*/}
                <Route path='/line' element={<Line/>  } />            
                <Route path='/area' element={<Area/> } />         
                <Route path='/bar' element={<Bar/>  } />  
                <Route path='/pie' element={<Pie/>} />   
                <Route path='/financial' element={<Financial/>} />
                <Route path='/colorMapping' element={<ColorMapping />} />
                <Route path='/pyramid' element={<Pyramid/>} />
               <Route path='/stacked' element={<Stacked/>} />
          </Routes>
        </div>
       
        </div>
      </BrowserRouter>
    </div>
  
  )
}

export default App