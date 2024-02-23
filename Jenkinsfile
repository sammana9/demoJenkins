pipeline{
agent any
stages{
stage('userfetch'){
steps{

wrap([$class:'BuildUser']){
 //echo "username: ${BUILD_USER}"
 script{
 def usrname: ${Build_USER}
 if(usrname=='admin')
 {
 echo 'suresh can only build this'
 }
 else{
 
 echo 'no one can build this except suresh'
 }
 }
}

}
}
}
}
