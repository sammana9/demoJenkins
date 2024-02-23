pipeline{
agent any
stages{
stage('userfetch'){
steps{

wrap([$class:'BuildUser']){

 script{
 def usrname: "${BUILD_USER}"
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
