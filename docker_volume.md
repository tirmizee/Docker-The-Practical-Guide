    
####  Bind Mounting

- Maps host file ไปยัง container file
- ไม่สามารถใช้ใน Dockerfile ได้ต้องอยู่ในคอนเทนเนอร์

    
        run -v /Users/bret/stuff:/path/container (mac/linux)

        run -v //c/Users/bret/stuff:/path/container (windows)
        
        run -v $(pwd):/app (macOS/Linux)

        run -v "%cd%":/app (Windows)
