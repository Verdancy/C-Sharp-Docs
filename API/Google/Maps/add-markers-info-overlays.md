### Add markers, info windows, and overlays to maps

To add markers, info windows, and overlays to a map in C# using the Google Maps API, you can use the following classes and methods:

1. GMapOverlay: Use this class to create a new overlay, which is a container for markers and other overlays. You can add one or more overlays to a GMapControl object using the Overlays property.
2. GMapMarker: Use this class to create a new marker, which is a visual representation of a specific location on the map. You can add markers to an overlay using the Markers property.
3. GMapInfoWindow: Use this class to create a new info window, which is a pop-up window that displays information about a marker when the marker is clicked. You can set the Content property of the GMapInfoWindow to specify the content to display in the info window.
4. GMapPolygon: Use this class to create a new polygon, which is a closed shape defined by a set of coordinates. You can add a polygon to an overlay using the Polygons property.

Here is some sample code that demonstrates how to add markers, info windows, and overlays to a map in C# using the Google Maps API:


```csharp
using System;
using System.Windows.Forms;
using GMap.NET;
using GMap.NET.MapProviders;

namespace GoogleMapsAPI
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();

            // Set the API key.
            GMap.NET.GMaps.Instance.ApiKey = "API_KEY"; // Replace "API_KEY" with your own API key.

            // Set the map provider and center the map on a specific location.
            gMapControl1.MapProvider = GoogleMapProvider.Instance;
            gMapControl1.SetPositionByKeywords("San Francisco, CA");
            gMapControl1.Zoom = 12;

            // Create a new overlay and add a marker and info window to it.
            GMapOverlay overlay = new GMapOverlay("overlay");
            GMapMarker marker = new GMapMarker(new PointLatLng(37.7749, -122.4194)); // Coordinates for San Francisco, CA.
            marker.ToolTipText = "San Francisco, CA";
            marker.ToolTipMode = MarkerTooltipMode.OnMouseOver;
            GMapInfoWindow infoWindow = new GMapInfoWindow();
            infoWindow.Content = new Label() { Text = "Welcome to San Francisco!" };
            infoWindow.Point = marker.Position;
            marker.Info = infoWindow;
            overlay.Markers.Add(marker);

            // Add a polygon to the overlay.
            List<PointLatLng> points = new List<PointLatLng>();
            points.Add(new LatLng(37.7000, -122.4167)); // Coordinates for San Francisco, CA.
			points.Add(new PointLatLng(37.7000, -122.4500)); // Coordinates for San Francisco, CA.
			points.Add(new PointLatLng(37.7833, -122.4500)); // Coordinates for San Francisco, CA.
			GMapPolygon polygon = new GMapPolygon(points, "polygon");
			polygon.Fill = new SolidBrush(Color.FromArgb(50, Color.Red));
			polygon.Stroke = new Pen(Color.Red, 1);
			overlay.Polygons.Add(polygon);

			// Add the overlay to the map.
			gMapControl1.Overlays.Add(overlay);
		}
	}
}
```

This code will create a new overlay with a marker and an info window, and a polygon. The marker will display a tooltip when the mouse is hovered over it, and the info window will be displayed when the marker is clicked. The polygon will be a red shape that is partially transparent. These elements will be added to the map when the overlay is added to the GMapControl object. You can customize the code to add additional markers, info windows, or polygons, or to modify the appearance of these elements.