# Android_RecyclerView
Android App Using RecyclerView &amp; Custom Adapter


# Code

#### MainActivity.java
```
String[] arr = {"item1", "item2", "item3", "item4", "item5", "item6", "item7", "item8", "item9", "item10"};
RecyclerView recyclerView;

recyclerView = findViewById(R.id.recyclerView);
recyclerView.setLayoutManager(new LinearLayoutManager(this));

CustomAdapter c = new CustomAdapter(arr);
recyclerView.setAdapter(c);
```

#### CustomAdapter.java
```
  public class CustomAdapter extends RecyclerView.Adapter<CustomAdapter.ViewHolder> {

    private String[] localDataSet;

    /**
     * Provide a reference to the type of views that you are using
     * (custom ViewHolder).
     */
    public static class ViewHolder extends RecyclerView.ViewHolder {
        private final TextView textView;

        public ViewHolder(View view) {
            super(view);
            // Define click listener for the ViewHolder's View

            textView = (TextView) view.findViewById(R.id.textView);
        }

        public TextView getTextView() {
            return textView;
        }
    }


     //1. Initialize the dataset of the Adapter (constructor)
    public CustomAdapter(String[] dataSet) {
        localDataSet = dataSet;
    }

    //2. Create new views (invoked by the layout manager)
    @Override
    public ViewHolder onCreateViewHolder(ViewGroup viewGroup, int viewType) {

        // Create a new view, which defines the UI of the list item
        View view = LayoutInflater.from(viewGroup.getContext())
                .inflate(R.layout.my_layout, viewGroup, false);

        return new ViewHolder(view);
    }

    //3. Replace the contents of a view (invoked by the layout manager)
    @Override
    public void onBindViewHolder(ViewHolder viewHolder, final int position) {

        // Get element from your dataset at this position and replace the
        // contents of the view with that element
        viewHolder.getTextView().setText(localDataSet[position]);
    }

    //4. Return the size of your dataset (invoked by the layout manager)
    @Override
    public int getItemCount() {
        return localDataSet.length;
    }
```

# App Highlight

<img src="app_images/Recycler View Custom Adapter Code.png" width="1000" /><br>

<img src="app_images/Recycler View Custom Adapter App.png" width="300" /><br>
