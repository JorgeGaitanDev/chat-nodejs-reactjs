cd Documents/
mkdir chat-nodejs-reactjs
cd chat-nodejs-reactjs
mkdir backend
cd backend/
npm init
npm install express cors axios
npm install --save-dev nodemon

"scripts": {
    "start": "nodemon index.js"
  },

se crea la carpeta index.js

https://blog.chatengine.io/fullstack-chat/nodejs-reactjs
const express = require("express");
const cors = require("cors");
const app = express();
app.use(express.json());
app.use(cors({ origin: true }));
app.post("/authenticate", async (req, res) => {
  const { username } = req.body;
  return res.json({ username: username, secret: "sha256..." });
});
app.listen(3001);

VERSION NODE DIFERENTE MINUTO 6

crear request.rest e instalar extension REST Client
POST https://localhost:3001/authenticate 
content-type: application/json
{ "username": "jorge" }

https://chatengine.io/projects/7f60d16d-eb90-4224-922d-6b640ff0bd8f
crear un char engine con api key
minuto 8
Project ID:
7f60d16d-eb90-4224-922d-6b640ff0bd8f
Private Key:
3963fe89-ecaa-4a95-b351-f25617c38f99 

https://rest.chatengine.io/

"Trabajando en este video actualmente. 
para cualquiera que se quede atrapado12:20, 
asegúrese de importar axios en la terminal: 
npm install axios. luego, en la parte superior 
del archivo index.js, debería estar: const 
express = require("express");
const cors = requerir("cors");
const axios = requerir('axios'); Funcionó 
para mí, espero que funcione para ti."

npm create vite@latest
frontend
javascrift
cd frontend

https://blog.chatengine.io/fullstack-chat/nodejs-reactjs
step 3:

version de node 18.19.1 para que coja vite

instalamos en la carpeta de fronteb
npm install axios

opcion 1 npm i react-chat-engine-advanced

ChatsPage.jsx
import { MultiChatSocket, MultiChatWindow, useMultiChatLogic } from 'react-chat-engine-advanced'

const ChatsPage = (props) => {
    const chatProps = useMultiChatLogic(
        '7f60d16d-eb90-4224-922d-6b640ff0bd8f', 
        props.user.username, 
        props.user.secret
    );
    return (
        <div style={{ height: '100vh' }}>
            <MultiChatSocket {...chatProps} />
            <MultiChatWindow {...chatProps} style={{ height: '100%'}} />    
        </div>
    )
}

export default ChatsPage


otra opcion (npm i react-chat-engine-pretty)
import { PrettyChatWindow } from 'react-chat-engine-pretty'

const ChatsPage = (props) => {
    return (
        <div style={{ height: '100vh' }}>
           <PrettyChatWindow
                projectId='
                7f60d16d-eb90-4224-922d-6b640ff0bd8f'
                username={props.user.username}
                secret={props.user.secret}
                style={{ height: '100%' }}
            />
        </div>
    )
}

export default ChatsPage

en backend npm run start
en frontend npm run dev
