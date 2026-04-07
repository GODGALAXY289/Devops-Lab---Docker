  pipeline{
    agent any
    stages{
      stage('#1. Checkout'){
        steps{
          git url:"https://github.com/GODGALAXY289/Devops-Lab---Docker", branch:'main'
        }
      }
      
      stage('#2. Build the image'){
        steps{
          bat 'docker build -t mywebsite .'
        }
      }

      stage('#3. Stop all old containers'){
        steps{
          bat 'docker stop mycontainer || exit 0'
          bat 'docker rm mycontainer || exit 0'
        }
      }

      stage('#4. Run the image'){
        steps{
          bat 'docker run -d -p 4000:80 --name mycontainer mywebsite'
        }
      }
    }
  }
