# My BookWorld

## Team members
* Neha Khairnar- nehak2209pc@gmail.com
* Prerna Shelke - prernashelke01@gmail.com
* Nishtha Sainger - nish279rs@gmail.com
* Meera Wadher - wadher.meera@gmail.com
* Gauri Shewale - gaurishewale08@gmail.com

## Mentors
* Palak Mantry
* Hrishikesh Bhagwat

## Table of Contents

* [About the Project](#about-the-project)
  * [Description](#Description)
  * [Tech Stack](#tech-stack)
  * [File Structure](#file-structure)
* [Future Scope](#future-scope)
* [Screenshots](#Screenshots)


## About The Project
Nowadays, everyone gets a platform and an opportunity to show their skills like dancing, singing, drawing, etc. with the help of social media applications and the internet. It doesn’t matter if their skills are professional or not but the important point here is that one gets the opportunity to show their talent to the whole world using those social media platforms. Similarly, writing is also one of the skills that a person can have. Not every writer is a professional one, some people write just for having fun, or some cherish writing as their hobby. But how could one know if he is a good writer or not and for that he needs to get a platform to display his work so that he can improve his skill and get motivated for working more hard in the future. Also, to be a good writer one should also be a good reader too. 
So, here we are with a special platform not only for all the enthusiastic writers but also for the readers out there. This platform will help the writers to showcase their talent to the world and will keep them motivated to work hard as a writer and also will make the readers happy by providing them with amazing stories

## Description  
My Book World is an android application developed as a part of Skill Up 2.0, an event organized by DSC  VJTI and COC VJTI. It is a kotlin based android application developed for the purpose of reading and writing books. The user can read books of different genres using this application and he can also publish his own book using this app as a platform by simply uploading a pdf of the book he has written. The features of this app include signing up, reading, and writing books and a list of sorted books according to categories which makes it user-friendly and easy to handle. All the data about users and books are stored and managed using firebase.



## Code Snippets
<hr>

##### Activity Intro (  For SignIn / SignUp Page )

```<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/intro_background"
    android:gravity="center_horizontal"
    android:orientation="vertical"
    tools:context=".ui.activities.IntroActivity">

    <TextView
        android:id="@+id/tv_app_name_intro"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginTop="@dimen/intro_screen_title_text_marginTop"
        android:fontFamily="@font/roboto_thin"
        android:text="@string/app_name"
        android:textColor="@color/darkteal_p"
        android:textSize="@dimen/intro_screen_title_text_size"
        android:textStyle="bold" />
```
##### Customized Styling for App ( Themes )
```<style name="AppTheme" parent="Theme.MaterialComponents.Light.NoActionBar">
        <!-- Customize your theme here. -->
        <item name="colorPrimary">@color/purple_500</item>
        <item name="colorPrimaryDark">@color/purple_700</item>
        <item name="colorAccent">@color/white</item>
        <item name="colorSecondary">@color/boysenberry</item>
    </style>

    <style name="AppTheme.NoActionBar">
        <item name="windowActionBar">false</item>
        <item name="windowNoTitle">true</item>
    </style>
    <style name="AppTheme.AppBarOverlay" parent="ThemeOverlay.MaterialComponents.Dark.ActionBar"> </style>
    <style name="AppTheme.PopupOverlay" parent="ThemeOverlay.MaterialComponents.Light"> </style>
```
##### Function to Get the Books List
```fun getBooksList(fragment: Fragment){
      mFireStore.collection(Constants.BOOKS)
            .get()
            .addOnSuccessListener { document->
                Log.e("books list", document.documents.toString())
                val bookList:ArrayList<Books> = ArrayList()
                for ( i in document.documents){
                    val book=i.toObject(Books::class.java)
                    book!!.book_id=i.id
                    bookList.add(book)

                }

                when(fragment){
                    is HomeFragment -> {

                        fragment.successProductListFromFireStore(bookList)
                    }
                }
            }
        .addOnFailureListener { exception ->
            Log.d(TAG, "Error getting documents: ", exception)
        }


    }
```
##### Books Model 
```data class Books(
        var book_id: String = "",
        val title: String ="",
        val author: String ="",
        val imageUrl: String ="",
        val bookUrl: String ="",
        val pages: String ="",
        val rating: String  ="",
        val review: String  ="",
        val description: String  ="",
        val category: String="",
        var user_id:String="",
        var id:String=""
):Parcelable
```
##### Book Details entered by Users are validated
```private fun validateBookDetails():Boolean{
        return when{
            mSelectedImageFIleUri == null ->{
                showErrorSnackBar(resources.getString(R.string.err_msg_select_book_cover), false)
                false
            }
            mBookUri == null ->{
                showErrorSnackBar(resources.getString(R.string.err_msg_select_book), false)
                false
            }
            bookCategory == null ->{
                showErrorSnackBar(resources.getString(R.string.err_msg_select_category), false)
                false
            }
            TextUtils.isEmpty(et_author_name.text.toString().trim {
                it <= ' '
            }) -> {
                showErrorSnackBar(resources.getString(R.string.err_msg_enter_name), false)
                false
            }
```


* GitHub repo link: [Link to repository](https://github.com/nehak2209/MyBookWorld)
* Drive link: [Drive link here](https://drive.google.com/file/d/1qR0LP-h-iVgQfeIwYiCvAYOBQy1-SE6H/view?usp=drivesdk)

### Tech Stack
* Languages
    * Kotlin
* Tools
 * [Kotlin](https://kotlinlang.org/)
 * [Firebase](https://firebase.google.com/)

### File Structure
```
.
|___MyBookWorld
|         |____app
|               |____src
|        	            |____main
|                             |____assets
|                             |____java/com/example/mybookworld
|                             |                   |____Firebase
|                             |                   |____models
|                             |                   |____ui
|                             |                   |____utils			
|                             |____res
|                             |     |____drawables
|                             |     |____font
|                             |     |____layout
|                             |     |____menu
|                             |     |____navigation
|                             |     |____values
|                             |
|                             |____AndroidManifest.xml
|              	             
|___screenshots

```

## Applications
<!-- >How can your project do its part in solving a real-life problem? What are its possible applications? Describe here.-->
Some of the main applications or features of this app.
* Easy to use and has simple features and navigation.
* Can be used to read books, and users can upload their own books too!
* Books uploaded can be of unlimited pages and in pdf format. They are uploaded genrewise.
* One can rate books and also add their favorite books to the favorite sections!
* Each user has his/her own profile.
* Each user can see his/her own books in the 'My Books' Section. 



## New Skills learnt from this project

1. Neha Khairnar-
    * Android app development using kotlin.
    * Storage and retrieval of data using firebase.
    * Working with a team.
    * Designing a good User Interface.
    * Working on a project using Github.
2. Nishtha Sainger-
    * Learnt Kotlin
    * Working on a group project
    * Learnt about firebase and its functioning
	
3. Prerana Shelke-
    * Learnt kotlin language.
    * Android development 
    * Creative Ui design.
    * Cloud firestore for database.
4. Meera Wadher -
    * Basics of Android App Development
    * Learnt about Android Material Design Basics
    * Styling of App and Color Themes
    * Learned Kotlin
5. Gauri Shewale -
    * Android app development using kotlin
    * Retrieval of data from firebase and selective display of the same
    * Setup of Bottom Navigation in the app
    * Learnt about Minimalist  UI design


## Future Scope
* Adding a comment section for readers.
* Recommending a book to the user according to his taste.
* Notifying users about newly uploaded books.
* Feature of rating the writer’s work by a reader


## Screenshots 
<!--
!<img src="https://github.com/preranashelke/get_maid/blob/master/180c13e8-d97c-4278-82e7-6b6ad2cac497.jpg" height = 450/> 

* GitHub repo link: ![Link to repository] (https://github.com/nehak2209/MyBookWorld)
* Drive link: ![Drive link here] (https://drive.google.com/file/d/1G6_kM6G92sUs4UPhozEpbKNYWcm1dFXQ/view?usp=sharing)
* Demo video: ![Drive link here] (https://drive.google.com/file/d/1GAwWDkzzA2KMJeEMtsRtmcMgrg71QY3w/view?usp=sharing)
-->
<img src="https://github.com/nehak2209/MyBookWorld/blob/master/screenshots/startpage.jpeg" height=450/>

<img src="https://github.com/nehak2209/MyBookWorld/blob/master/screenshots/sign_in.jpeg" height=450/>

<img src="https://github.com/nehak2209/MyBookWorld/blob/master/screenshots/books.jpeg" height=450/>

<img src="https://github.com/nehak2209/MyBookWorld/blob/master/screenshots/Options_Drawer.jpeg" height=450/>

<img src="https://github.com/nehak2209/MyBookWorld/blob/master/screenshots/categories.jpeg" height=450/>

<img src="https://github.com/nehak2209/MyBookWorld/blob/master/screenshots/fantasy_genre_books.jpeg" height=450/>

<img src="https://github.com/nehak2209/MyBookWorld/blob/master/screenshots/book_desc.jpeg" height=450/>

<img src="https://github.com/nehak2209/MyBookWorld/blob/master/screenshots/favorites.jpeg" height=450/>

<img src="https://github.com/nehak2209/MyBookWorld/blob/master/screenshots/upload_work.jpeg" height=450/>

<img src="https://github.com/nehak2209/MyBookWorld/blob/master/screenshots/update_profile.jpeg" height=450/>

<img src="https://github.com/nehak2209/MyBookWorld/blob/master/screenshots/help_contact.jpg" height=450/>