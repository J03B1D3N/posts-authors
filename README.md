@click Save button, i take the values from the from into an object that looks like this:
{
    title: form.title.value
    authorId: postDetail.authorId
    body: form.body.value
    created_at: postDetail.created_at
    updated_at: getDate()
}


getDate() {
    const date = new date()
    const month = date.getMonth()
    cont day = date.getDay()
    const year = date.getYear()
    return `${year}-${month}-%{day}`
}



add modal overlay done
valdiate the edit form done
add overlay for the deletePost message done
hide modal with v-show instead of v-if done
edit success and failure popups to have only one method that accepts an object done
change modalOpen and modalClose into one method called modalToggle, which sets state = !state done
clean unused imports done


