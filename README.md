Mrs Bake Cafe Meal Suggestion App
The purpose of the application is to provide some coniveince to a customer. The application allows the user to select meals based on the time of day. There are specific foods for different times of the day thats are easy to read and eye catching. The application needs to offer dietry options and included a detailed list of ingredients. The user needs to be able to customize their order should thre be an ingredient they are allergic to or dont like. It needs to also have a reset option to clear the selection if an incorrect option has beebn selected. The application needs to be user friendly and easy to follow instructions and quick to respond..If there are eroors, it should be able to provide feedback on those errors and some guidance to rectify the errors. 

package com.example.mrsbakecafe

import android.R.attr.end
import android.R.attr.label
import android.annotation.SuppressLint
import android.os.Bundle
import android.view.View
import android.widget.TextView
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.activity.enableEdgeToEdge
import androidx.compose.foundation.layout.Column
import androidx.compose.foundation.layout.Row
import androidx.compose.foundation.layout.fillMaxSize
import androidx.compose.foundation.layout.padding
import androidx.compose.material3.Button
import androidx.compose.material3.Label
import androidx.compose.material3.OutlinedTextField
import androidx.compose.material3.Scaffold
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.runtime.MutableState
import androidx.compose.runtime.getValue
import androidx.compose.runtime.mutableStateOf
import androidx.compose.runtime.remember
import androidx.compose.runtime.setValue
import androidx.compose.ui.Modifier
import androidx.compose.ui.layout.BeyondBoundsLayout.LayoutDirection.Companion.Below
import androidx.compose.ui.tooling.preview.Preview
import com.example.mrsbakecafe.ui.theme.MrsBakeCafeTheme
import org.w3c.dom.Text
import android.widget.EditText
import android.widget.TextView


private var Any.text: String
private val MainActivity.suggestionsDisplay: Any
private val MainActivity.endif: Unit
private val MainActivity.timeofday: Any

class MainActivity : ComponentActivity() {
    @Composable
    @SuppressLint("RememberReturnType")
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()
        setContent {
            MrsBakeCafeTheme {
                var timeofday by remember {
                    mutableStateOf("")
                }

                val mealsuggestions by remember {
                    mutableStateOf("")
                }

                Column {
                    Text("Mrs Bake Cafe")
                    OutlinedTextField(
                        value = timeofday,
                        onValueChange = { text ->
                            timeofday = text
                        }
                    )
                }

                Row {
                    Button(
                        onClick = {

                        }
                    ) {
                        Text("Next")
                    }

               Row{
                   Button(
                       onClick = {

                       }
                   ) {
                       Text(text="Rest")
                   }
               }

                    var timeofday by remember {
                        mutableStateOf("Morning")

                    }
                    if (timeofday == "Morning") {
                        Text(text = "Breakfast")

                    } else (timeofday == "Mid-Morning")
                    Text(text = "Light snack")
                }

                if (timeofday == "Afternoon") {
                    Text(text = "Lunch")

                } else (timeofday == "Mid-Afternoon")
                Text(text = "Snack")
            }

            if (timeofday == "Dinner")
                Text(text = "Main Course")
            else (timeofday == "After Dinner")
            Text(text = "Dessert")

            endif
        }

        fun suggestMeal(view: View) {
            val timeOfDay inputTime.text.toString().trim(.toLowerCase()

            var suggestions = ""

             if (timeofday == "morning") {
                 suggestions = "Omlette, Pancakes, English Breakfast"
             }  else if (timeofday == "Mid-Morning") {
                 suggestions = "Apple"
             }  else if (timeofday == "Afternoon") {
                 suggestions = "Sandwich, Pizza"
             }  else if (timeofday == "Mid-Afternoon") {
                 suggestions = "Salad"
             }  else if (timeofday == "Dinner") {
                 suggestions = "Pasta, Stir Fry"
             }else if (timeofday == "After Dinner") {
                 suggestions = "Ice Cream"
             }

            suggestionsDisplay.text = "Meal Suggestions: $suggestions"
        }
    }
}
